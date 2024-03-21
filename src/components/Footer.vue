<script>
export default {
  data() {
    return {
      menuInfo: [
        {
          title: "Informazioni legali",
          link: "#",
        },
        {
          title: "Informativa sulla privacy",
          link: "#",
        },
        {
          title: "Diritto di recesso",
          link: "#",
        },
      ],
      menuIcon: [
        {
          title: '<i class="fa-brands fa-square-twitter"></i>',
          link: "#",
        },
        {
          title: '<i class="fa-brands fa-square-facebook"></i>',
          link: "#",
        },
        {
          title: '<i class="fa-brands fa-square-instagram"></i>',
          link: "#",
        },
        {
          title: '<i class="fa-brands fa-square-pinterest"></i>',
          link: "#",
        },
        {
          title: '<i class="fa-brands fa-square-youtube"></i>',
          link: "#",
        },
      ],
    };
  },
};
</script>

<template>
  <footer>
    <div class="bottom-bar">
      <div class="box">
        <div class="info">
          <h4>Boolando s.r.l.</h4>
          <!-- nav -->
          <nav class="menu">
            <ul>
              <li v-for="(item, index) in menuInfo" :key="index">
                <a :href="item.link">{{ item.title }}</a>
              </li>
            </ul>
          </nav>
          <!-- /nav -->
        </div>

        <div class="social">
          <span>Trovaci anche su</span>
          <!-- nav -->
          <nav class="menu">
            <ul>
              <li v-for="(item, index) in menuIcon" :key="index">
                <!-- <a href="#"><i class="fa-brands fa-square-twitter"></i></a> -->
                <a :href="item.link" v-html="item.title"></a>
              </li>
              <!-- <li>
                <a href="#">Facebook</a>
                <a href="#"><i class="fa-brands fa-square-facebook"></i></a>
              </li>
              <li>
                <a href="#">Instagram</a>
                <a href="#"><i class="fa-brands fa-square-instagram"></i></a>
              </li>
              <li>
                <a href="#">Pinterest</a>
                <a href="#"><i class="fa-brands fa-square-pinterest"></i></a>
              </li>
              <li>
                <a href="#">YT</a>
                <a href="#"><i class="fa-brands fa-square-youtube"></i></a>
              </li> -->
            </ul>
          </nav>
          <!-- /nav -->
        </div>
      </div>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/variables" as *;

.bottom-bar {
  // DEBUG
  position: absolute;
  top: calc(100% - 90px);
  // /DEBUG
  width: 100%;
  background-color: $bg-color-bottom-bar;
  color: $color-menu-a;
  height: 90px;
  .box {
    margin: 0 17%;
    .info .menu a {
      font-size: 0.8rem;
    }
  }
}
</style>
