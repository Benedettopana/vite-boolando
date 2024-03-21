<script>
// Supports weights 100-700
import "@fontsource-variable/material-symbols-rounded";
export default {
  data() {
    return {};
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
            <li>
              <a href="#">Donna</a>
            </li>
            <li>
              <a href="#">Uomo</a>
            </li>
            <li>
              <a href="#">Bambini</a>
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
            <li>
              <a href="#">person</a>
            </li>
            <li>
              <a href="#">favorite</a>
            </li>
            <li>
              <a href="#">shopping_cart</a>
            </li>
          </ul>
        </nav>
        <!-- /icon -->
      </div>
    </div>
  </header>
</template>

<style lang="scss">
.topbar {
  background-color: #ff6900;
  width: 100%;
  height: 60px;
  position: fixed;
  z-index: 1;
  top: 0;
  left: 0;
}

.logo {
  width: 300px;
}

.logo img {
  max-width: 30%;
}

.social {
  font-family: "Material Symbols Rounded Variable";
}
.menu ul {
  display: flex;
  list-style: none;
  justify-content: space-between;
}

.menu ul a {
  color: white;
  text-decoration: none;
  margin-right: 10px;
}

.menu ul a:hover {
  text-decoration: underline;
}
</style>
