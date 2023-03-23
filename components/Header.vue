<template>
  <header class="header">
    <nuxt-link to="/" class="logo">
      <!-- Update your site logo text -->
      Wittness
    </nuxt-link>
    <input class="menu-btn" type="checkbox" id="menu-btn" v-model="menuChecked" />
    <label class="menu-icon" for="menu-btn"><span class="navicon"></span></label>
    <ul class="menu">
      <!-- Page Links -->
      <li><nuxt-link to="/blog" @click.native="menuChecked = false">Blog</nuxt-link></li>
      <li><nuxt-link to="/contact" @click.native="menuChecked = false">Contact</nuxt-link></li>
      <li><nuxt-link to="/about" @click.native="menuChecked = false">About Us</nuxt-link></li>
      <!-- Add a menu:
   Log in / Sign up - when the user is not logged in
   Username / Log out - when the user is logged in
  -->
      <li>
        <div class="button-primary" data-netlify-identity-menu></div>
      </li>

      <!-- Add a simpler button:
  Simple button that will open the modal.
-->
      <!-- <div data-netlify-identity-button>Login with Netlify Identity</div> -->
    </ul>
  </header>
</template>

<script>
export default {
  props: ['menuChecked'],
  mounted() {
    if (window.netlifyIdentity) {
      window.netlifyIdentity.on("init", user => {
        if (!user) {
          window.netlifyIdentity.on("login", () => {
            document.location.href = "/admin/";
          });
        }
      });
    }
  }
}


</script>