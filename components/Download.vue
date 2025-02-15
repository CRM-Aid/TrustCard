<template>
  <div id="downloadSection" class="mt-16">
    <h2 class="font-extrabold text-2xl">Download</h2>
    <div class="stepC mt-6">
      <p>Please complete the checklist to proceed,</p>
      <Check
        v-for="(item, index) in downloadCheckList"
        :downloadCheckList="downloadCheckList"
        :item="item"
        :key="index"
        :index="index"
      />
      <button
        ref="downloadPackage"
        @click="downloadPackage"
        class="inline-block bg-gray-700 leading-none text-2xl tracking-wide border-2 border-transparent font-extrabold p-6 rounded mt-12 select-none transition-colors duration-200 focus:outline-none"
        :title="
          downloadChecked
            ? ''
            : 'Complete the checklist to download the package'
        "
        :class="
          downloadChecked
            ? 'bg-green-600 cursor-pointer text-white focus:bg-green-500 hover:bg-green-500'
            : 'text-black nopointerEvent '
        "
      >
        <!-- put this after colon once you done with proje -->
        <!-- cursor-not-allowed text-black -->
        Download as ZIP
      </button>
      <p class="mt-6 border p-4 rounded border-gray-700 text-gray-400">
        <span class="font-extrabold text-2xl" style="color: #ffffff"
          >After You Download...</span
        >
        <br /><br /><span><strong>DO IT YOURSELF</strong></span
        ><br />
        Extract the downloaded ZIP file and follow the
        <NuxtLink
          to="/hosting-guide"
          class="cursor-pointer underline font-extrabold text-emerald-500 hover:text-emerald-400 focus:text-emerald-500 transition-colors duration-200"
          >Hosting&nbsp;Guide</NuxtLink
        >
        to get your digital business card online.
        <br /><br />
        <span><strong>DONE FOR YOU</strong> (CRM-Aid Users)</span><br />
        Upload your ZIP file and we will take care of everything for you. We
        will send you your branded vCard Builder in 1 business day!
        <button
          @click="showModal = true"
          class="flex flex-row justify-center font-extrabold leading-none text-xl tracking-wide rounded transition-colors duration-200 focus:outline-none bg-gray-700 border-2 border-transparent p-4 mt-4 select-none"
          :title="
            downloadChecked
              ? ''
              : 'Complete the checklist to download the package'
          "
          :class="
            downloadChecked
              ? 'bg-green-600 cursor-pointer text-white focus:bg-green-500 hover:bg-green-500'
              : 'text-black nopointerEvent '
          "
        >
          Upload
        </button>
      </p>
      <!-- Vcard upload form Modal start's here -->
      <div
        v-if="showModal"
        class="fixed inset-0 z-50 flex items-center justify-center bg-black bg-opacity-50 overflow-auto"
      >
        <div class="relative w-full max-w-3xl bg-white rounded-2xl shadow-lg">
          <!-- Close button in top right corner -->
          <button
            @click="showModal = false"
            class="absolute top-4 right-4 text-white hover:text-gray-200 bg-red-500 rounded-full p-1"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
              stroke-width="2"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>

          <h2 class="mb-4 text-xl font-semibold px-4 mt-4 text-gray-800">
            vCard Deployment Form
          </h2>
          <p class="mb-4 text-gray-600 px-4">
            Submit your vCard ZIP file and details to get it integrated with
            your website based on your agency setup.
          </p>

          <!-- Embedded form -->
          <div class="overflow-y-auto" style="max-height: 100vh">
            <iframe
              src="https://api.crmaid.ai/widget/form/9VYCgz21Rn4PMhjBZCQf"
              style="
                width: 100%;
                height: 100%;
                border: none;
                border-radius: 3px;
              "
              id="inline-9VYCgz21Rn4PMhjBZCQf"
              data-layout="{'id':'INLINE'}"
              data-trigger-type="alwaysShow"
              data-trigger-value=""
              data-activation-type="alwaysActivated"
              data-activation-value=""
              data-deactivation-type="neverDeactivate"
              data-deactivation-value=""
              data-form-name="Upload vCard Form"
              data-height="708"
              data-layout-iframe-id="inline-9VYCgz21Rn4PMhjBZCQf"
              data-form-id="9VYCgz21Rn4PMhjBZCQf"
              title="Upload vCard Form"
            ></iframe>
            <script src="https://api.crmaid.ai/js/form_embed.js"></script>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Check from '@/components/Check'
export default {
  props: ['downloadCheckList', 'downloadChecked', 'downloadPackage'],
  components: {
    Check,
  },
  data() {
    return {
      showModal: false,
    }
  },
}
</script>
<style>
.nopointerEvent {
  pointer-events: none;
  cursor: not-allowed;
}
</style>
