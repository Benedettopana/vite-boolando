<script>
// import components
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import Footer from "./components/Footer.vue";
// FontAwesome
// import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
// import { byPrefixAndName } from '@awesome.me/kit-KIT_CODE/icons'

export default {
  components: {
    Header,
    Main,
    Footer,
  },
};
</script>

<template>
  <div>
    <Header />
    <Main />
    <Footer />
  </div>
</template>

<style lang="scss">
@import "./assets/scss/main.scss";
</style>
