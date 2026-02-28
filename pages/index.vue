<template>
  <div class="home-container">
    <div class="u-full-width">
      <h1 class="site-title">
        <!-- Define Custom Site title or completely change the page -->
        Witt<span class="txt-color">ness </span>! Tech
      </h1>
      <div>
        The 
        <a href="wittness.netlify.app" class="green">
        main
          </a>
        site is no more under construction.
      </div>
      <!-- <a class="no-highlighter" href="https://github.com/gms64/nuxt-static-skeleton" target="_blank">
        <button class="button-primary">
          See the Repo
        </button>
      </a> -->

    </div>
    <!-- This is used to load the netlify identity widget so you can use Netlify CMS -->
    <script async src="https://identity.netlify.com/v1/netlify-identity-widget.js"></script>
  </div>
</template>

<script>
export default {
  // Define SEO Variables / Site Title, etc.
  head() {
    return {
      title: this.siteName || 'W - Home Page',
      meta: [
        {
          hid: 'w - description',
          name: 'w - descriptionName',
          content: 'A website created fpr Wittness Tech.'
        }
      ]
    };
  },
  async asyncData({ env }) {
    const siteName = env.SITE_NAME
    return {
      siteName
    }
  }
}
</script>

