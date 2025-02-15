<template>
  <div class="mediaC">
    <div>
      <img :src="media.coverDataURI || defaultImage" :alt="media.title" />
    </div>
    <div class="controls cardColor">
      <p class="title">
        {{ media.title }}
      </p>
      <div class="docDl">
        <p class="fileSize sub">PDF - {{ media.filesize }}</p>
        <a
          class="dlBtn"
          :style="{ backgroundColor: `${colors.buttonBg.color}` }"
          :href="pdfDataURI"
          :download="`${getTitle(media.title)}.pdf`"
          target="_blank"
        >
          <div
            class="icon iconColor"
            v-html="require(`~/assets/icons/download.svg?include`)"
          ></div>
        </a>
      </div>
    </div>
  </div>
</template>

<script>
import { saveAs } from 'file-saver'

export default {
  props: ['media', 'type', 'colors', 'PreviewMode'],
  data() {
    return {
      pdfDataURI: '',
      defaultImage: 'data:image/png;base64,...', // Replace with a default image base64 string
    }
  },
  mounted() {
    this.convertFileToBase64(this.media.file, 'application/pdf').then(
      (base64) => {
        this.pdfDataURI = base64
      }
    )

    if (!this.media.coverDataURI) {
      this.convertFileToBase64(this.media.cover, 'image/png').then((base64) => {
        this.media.coverDataURI = base64
      })
    }
  },
  methods: {
    getTitle(e) {
      return e.toLowerCase().split(' ').join('_')
    },
    convertFileToBase64(file, mimeType) {
      return new Promise((resolve, reject) => {
        const reader = new FileReader()
        reader.readAsDataURL(file)
        reader.onload = () => resolve(reader.result)
        reader.onerror = (error) => reject(error)
      })
    },
    downloadDocument() {
      saveAs(
        window.URL.createObjectURL(this.media.file),
        `${this.media.title}.pdf`
      )
    },
  },
}
</script>
