<script>
// Supports weights 100-700
import "@fontsource-variable/material-symbols-rounded";

export default {
  data() {
    return {
      menuSection: [
        {
          title: "Donna",
          link: "#",
        },
        {
          title: "Uomo",
          link: "#",
        },
        {
          title: "Bambini",
          link: "#",
        },
      ],
      menuIcon: [
        {
          icon: '<i class="fa-regular fa-user"></i>',
          link: "#",
        },
        {
          icon: '<i class="fa-regular fa-heart"></i>',
          link: "#",
        },
        {
          icon: '<i class="fa-solid fa-bag-shopping"></i>',
          link: "#",
        },
      ],
    };
  },
};
</script>

<template>
  <header>
    <div class="topbar">
      <div class="box">
        <!-- nav -->
        <nav class="menu">
          <ul>
            <li v-for="(item, index) in menuSection" :key="index">
              <a :href="item.link">{{ item.title }}</a>
            </li>
          </ul>
        </nav>
        <!-- /nav -->

        <!-- logo -->
        <div class="logo">
          <img src="../assets/img/boolean-logo.png" alt="logo" />
        </div>
        <!-- /logo -->

        <!-- icon -->
        <nav class="menu social">
          <ul>
            <li v-for="(item, index) in menuIcon" :key="index">
              <a :href="item.link" v-html="item.icon"></a>
            </li>
          </ul>
        </nav>
        <!-- /icon -->
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/variables" as *;

.topbar {
  background-color: $bg-color-top-bar;
  width: 100%;
  height: 60px;
  position: fixed;
  z-index: 1;
  top: 0;
  left: 0;
  .logo {
    width: 300px;
    img {
      max-width: 30%;
    }
  }

  .social {
    font-family: "Material Symbols Rounded Variable";
  }
}
</style>
