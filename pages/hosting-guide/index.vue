<template>
  <div class="bg-gray-900 mx-auto text-gray-100" style="max-width: 960px">
    <div class="px-4">
      <div class="flex items-start justify-between pt-8">
        <NuxtLink to="/">
          <img
            src="../../assets/icons/logo_1.png"
            class="logo w-16"
            alt="TrustCard- An Open-Source Digital Business Card Generator"
          />
        </NuxtLink>
        <a
          class="font-extrabold tracking-wide leading-none shrink-0 p-3 border-2 text-white border-gray-700 rounded hover:bg-gray-700 transition-colors duration-200"
          href="https://app.crmaid.ai"
          target="_blank"
          rel="noreferrer"
          >Login</a
        >
      </div>
      <div id="guide" class="max-w-screen-sm">
        <h1 class="text-3xl md:text-5xl font-extrabold mt-8 md:leading-tight">
          Hosting Guide
        </h1>
        <h2 class="mt-8 text-lg md:text-xl w-full md:w-3/4 text-gray-200">
          Please follow the instructions as per your category to get your
          digital business card online.
        </h2>

        <p class="mt-16 border px-4 py-3 rounded border-gray-700">
          Your digital business card files are located in the folder you just
          extracted from your downloaded ZIP file. Navigate to
          <span class="font-extrabold"> yourname's TrustCard </span> >
          <span class="font-extrabold">yourname (folder)</span>—this contains
          all the necessary files except the GHL folder, which I'll explain
          later. Throughout this guide, we'll refer to this as the "<span
            class="font-extrabold"
            >TrustCard folder</span
          >".
        </p>

        <div class="mt-16">
          <h3 class="font-extrabold text-2xl">
            I have a personal WordPress website
          </h3>
          <ul class="px-6 mt-6 list-outside list-disc">
            <li>
              Login to your cPanel account. Locate and open the file manager.
            </li>
            <li>
              In the file manager, locate the folder named "public_html" and
              create a new folder called "vcard" ( or whatever you like ) inside
              it.
            </li>
            <li>
              Upload your <b>TrustCard folder</b> into the new folder that you
              just created in the previous step.
            </li>
            <li>
              Now your business card should be online at the address
              https://your-domain.com/vcard/trustcard-folder-name/ and is ready
              to be shared.
            </li>
          </ul>
        </div>

        <div class="mt-16">
          <h3 class="font-extrabold text-2xl">
            I've a CRM powered by
            <a href="https://app.crmaid.ai" target="_blank" class="underline">
              CRM-Aid.
            </a>
          </h3>
          <ul class="px-6 mt-6 list-outside list-disc">
            <li>
              Log in to your CRM-Aid account. Navigate to the "Build" menu and
              select the "Website" tab from the dropdown to open the Website
              Builder.
            </li>
            <li>
              Inside the Website Builder, locate and open the "Digital
              TrustCards" folder. Click on it, then select "New Website" from
              the top menu. A modal will appear—choose "From Templates" to open
              the CRM-Aid Template Library. Go to "My Templates", find the
              TrustCard Template, and click on it. Then, click "Continue" to
              start editing the template.
            </li>
            <li>
              Next, click on "Custom HTML/JavaScript" and, on the right side,
              select "Open Code Editor". This will open a blank code editor.
              Now, open the GHL folder, where you'll find a file named
              "index.html", which contains all necessary assets. Open this file
              in any text editor, copy all its content (Ctrl + A, then Ctrl +
              C), and return to the Open Code Editor in CRM-Aid. Paste the
              copied code (Ctrl + V) and click the "Save" button in the navbar.
              Finally, publish the page under your domain to make it live.
            </li>
            <li>
              Your digital business card will now be accessible online at:
              https://your-domain.com/vcard/trustcard-folder-name/, ready to be
              shared.
            </li>
          </ul>
        </div>

        <div class="mt-16">
          <h3 class="font-extrabold text-2xl">
            My website is maintained by a developer
          </h3>
          <ul class="px-6 mt-6 list-outside list-disc">
            <li>
              Contact your developer to host the business card for you. Just
              send them the downloaded ZIP file.
            </li>
          </ul>
        </div>
        <div class="mt-16">
          <h3 class="font-extrabold text-2xl">
            We are a company. Our website is maintained by the IT team
          </h3>
          <ul class="px-6 mt-6 list-outside list-disc">
            <li>
              Just share the details with your IT team, let them create digital
              business cards for you using
              <NuxtLink
                to="/"
                class="underline font-extrabold text-emerald-600 hover:text-emerald-500 focus:text-emerald-500 transition-colors duration-200"
                >TrustCard</NuxtLink
              >.
            </li>
            <li>
              If you got some business cards created by yourself, contact your
              IT team to host it for you. Just send them the downloaded ZIP
              files and share the link to this
              <a
                class="underline font-extrabold text-emerald-600 hover:text-emerald-500 focus:text-emerald-500 transition-colors duration-200"
                href="https://trustcard.crmaid.ai/hosting-guide"
                target="_blank"
                @click.prevent="
                  copyToClipboard('https://trustcard.crmaid.ai/hosting-guide')
                "
              >
                Hosting Guide </a
              >.
            </li>
          </ul>
        </div>
        <div class="mt-16">
          <h3 class="font-extrabold text-2xl">
            I'm the developer / administrator of a website
          </h3>
          <ul class="px-6 mt-6 list-outside list-disc">
            <li>
              Create a folder called "vcard" ( or whatever you like ) in the
              project's static folder.
            </li>
            <li>Copy the <b>Trustcard folder</b> inside the "vcard" folder.</li>
            <li>Commit changes and deploy.</li>
            <li>
              Now the business card should be online at the address
              https://your-domain/vcard/trustcard-folder/ and is ready to be
              shared.
            </li>
          </ul>
        </div>
        <div class="mt-16">
          <h3 class="font-extrabold text-2xl">I don't have a website</h3>
          <p class="mt-6">
            You can host your digital business card using several free hosting
            services available such as
            <a
              class="underline font-extrabold text-emerald-600 hover:text-emerald-500 focus:text-emerald-500 transition-colors duration-200"
              href="https://surge.sh"
              target="_blank"
              rel="noopener noreferrer"
              >Surge</a
            >,
            <a
              class="underline font-extrabold text-emerald-600 hover:text-emerald-500 focus:text-emerald-500 transition-colors duration-200"
              href="https://pages.github.com/"
              target="_blank"
              rel="noopener noreferrer"
              >GitHub Pages</a
            >,
            <a
              class="underline font-extrabold text-emerald-600 hover:text-emerald-500 focus:text-emerald-500 transition-colors duration-200"
              href="https://docs.gitlab.com/ee/user/project/pages/"
              target="_blank"
              rel="noopener noreferrer"
              >GitLab Pages</a
            >, etc.
          </p>
          <ul class="px-6 mt-6 list-outside list-disc">
            <li>
              Follow the user guide of any of the services mentioned above to
              setup a website.
            </li>
            <li>
              Once done, copying your trustcard folder into a respective folder
              is all it needed to get your digital business card online. But the
              procedure might vary with platform.
            </li>
          </ul>
          <p class="mt-4">
            If you got any doubt setting up your digital business card on any of
            these platforms, You can always
            <a
              class="underline text-emerald-600 font-extrabold hover:text-emerald-500 focus:text-emerald-500 transition-colors duration-200"
              href="https://portal.crmaid.ai/communities/groups/trustcard/home?invite=67aeb83fe8c3f919f9f353be"
              target="_blank"
              rel="noopener noreferrer"
              >Join the TrustCard community!</a
            >
            and ask it.
          </p>
        </div>
        <div class="mt-16">
          <h3 class="font-extrabold text-2xl">
            How do I update my business card details?
          </h3>
          <p class="mt-6">
            TrustCard does not store any data online for you to retrieve it for
            editing. So, every card has to be manually created from scratch.
          </p>
          <ul class="px-6 mt-6 list-outside list-disc">
            <li>
              Visit
              <NuxtLink
                to="/"
                class="underline font-extrabold text-emerald-600 hover:text-emerald-500 focus:text-emerald-500 transition-colors duration-200"
                >TrustCard</NuxtLink
              >
              and generate a new digital business card.
            </li>
            <li>
              Extract the downloaded ZIP file and copy your trustcard folder
              containing your updated files.
            </li>
            <li>
              Follow the exact same steps as per your category listed above to
              update your digital business card.
            </li>
          </ul>
        </div>
        <div class="mt-16">
          <h3 class="font-extrabold text-2xl">
            How do I add another business card to my website?
          </h3>
          <ul class="px-6 mt-6 list-outside list-disc">
            <li>
              Visit
              <NuxtLink
                to="/"
                class="underline font-extrabold text-emerald-600 hover:text-emerald-500 focus:text-emerald-500 transition-colors duration-200"
                >TrustCard</NuxtLink
              >
              & generate a digital business card.
            </li>
            <li>
              Extract the downloaded ZIP file & copy the TrustCard folder.
            </li>
            <li>
              Follow the exact same steps as per your category listed above to
              add the digital business card.
            </li>
            <li>
              Place the copied folder inside the same folder where you already
              have your TrustCard folders.
            </li>
          </ul>
        </div>
      </div>
      <Help />
    </div>
    <Footer />
  </div>
</template>
<script>
import Footer from '@/components/Footer'
import Help from '@/components/Help'

export default {
  components: {
    Footer,
    Help,
  },
  methods: {
    copyToClipboard(url) {
      navigator.clipboard
        .writeText(url)
        .then(() => {
          alert('The Hosting Guide URL has been copied to your clipboard!')
          window.open(url, '_blank') // Open the link after copying
        })
        .catch((err) => console.error('Failed to copy:', err))
    },
  },
}
</script>
