<template>
  <div
    id="newsletter-form"
    class="flex flex-col lg:flex-row lg:justify-between lg:items-center"
  >
    <div class="flex-shrink lg:max-w-lg xl:max-w-xl mb-4 lg:mb-0">
      <h2>Stay informed</h2>
      <p class="mt-2 mr-2">
        Sign up for the IPFS Weekly newsletter (<a
          class="text-blueGreenLight hover:underline"
          href="https://blog.ipfs.io/?tags=weekly"
          >example</a
        >) for the latest on releases, upcoming developments, community events,
        and more.
      </p>
    </div>
    <form
      id="mc-embedded-subscribe-form"
      name="mc-embedded-subscribe-form"
      class="flex lg:justify-end max-w-2xl xl:w-3/5"
      action="https://ipfs.us4.list-manage.com/subscribe/post?u=25473244c7d18b897f5a1ff6b&amp;id=cad54b2230"
      method="post"
      target="_blank"
      @submit="onSubmit"
    >
      <div id="mc_embed_signup_scroll" class="grid gric-col-2 w-full">
        <div class="fields flex flex-col sm:flex-row col-start-1 col-span-2">
          <input
            id="mce-EMAIL"
            v-model="email"
            required
            type="email"
            aria-label="Email Address"
            class="flex-grow text-black p-2 rounded"
            placeholder="email@your.domain"
            name="EMAIL"
          />
          <div class="sm:ml-4 sm:pt-0 pt-2">
            <input
              id="mc-embedded-subscribe"
              type="submit"
              value="Subscribe"
              name="subscribe"
              class="p-2 text-white font-semibold bg-blueGreen hover:bg-blueGreenScreen transition duration-300 rounded cursor-pointer w-full"
            />
          </div>
        </div>
        <label class="pt-2 col-start-1 col-span-2" for="gdpr_28879">
          <input
            id="gdpr_28879"
            type="checkbox"
            class=""
            required
            name="gdpr[28879]"
            value="Y"
          /><span class="pl-2">Please send me the newsletter</span>
        </label>
      </div>
      <div id="mergeRow-gdpr">
        <div style="position: absolute; left: -5000px" aria-hidden="true">
          <input
            type="text"
            name="b_25473244c7d18b897f5a1ff6b_cad54b2230"
            tabindex="-1"
            value=""
          />
        </div>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: 'NewsletterForm',
  props: {},
  data: () => ({
    email: null,
  }),
  methods: {
    onSubmit() {
      this.$countly.trackEvent(this.$countly.events.NEWSLETTER_SUBSCRIBE);
    },
  },
};
</script>

<style scoped>
h2 {
  @apply font-display;

  font-weight: 500;
  font-size: 1.75rem;
  line-height: 1.2;
  letter-spacing: -0.01em;
}
</style>
