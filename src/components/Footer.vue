<script>
export default {
  data() {
    return {};
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
              <li>
                <a href="#">Informazioni legali</a>
              </li>
              <li>
                <a href="#">Informativa sulla privacy</a>
              </li>
              <li>
                <a href="#">Diritto di recesso</a>
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
              <li>
                <!-- <a href="#"><i class="fa-brands fa-square-twitter"></i></a> -->
                <a href="#">Twitter</a>
              </li>
              <li>
                <a href="#">Facebook</a>
                <!-- <a href="#"><i class="fa-brands fa-square-facebook"></i></a> -->
              </li>
              <li>
                <a href="#">Instagram</a>
                <!-- <a href="#"><i class="fa-brands fa-square-instagram"></i></a> -->
              </li>
              <li>
                <a href="#">Pinterest</a>
                <!-- <a href="#"><i class="fa-brands fa-square-pinterest"></i></a> -->
              </li>
              <li>
                <a href="#">YT</a>
                <!-- <a href="#"><i class="fa-brands fa-square-youtube"></i></a> -->
              </li>
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
  position: absolute;
  top: calc(100% - 90px);
  width: 100%;
  background-color: $bg-color-bottom-bar;
  color: white;
  height: 90px;
  .box {
    margin: 0 17%;
    .info .menu a {
      font-size: 0.8rem;
    }
  }
}
</style>
