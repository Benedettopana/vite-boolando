<script>
export default {
  name: "Product",
  props: {
    imgHide: String,
    img: String,
    brand: String,
    nameProduct: String,
    price: String,
    // title: String,
    // subPriceSale: String,
  },
  mounted() {},
};
</script>

<template>
  <!-- <div class="prodotto">
    <img :src="img" :alt="title" />
    <span class="marca">{{ subtitle }}</span>
    <h4 class="nome">{{ title }}</h4>
  </div> -->
  <div class="prodotto">
    <!-- img nascosta -->
    <img class="nascosta" :src="imgHide" :alt="title" />

    <!-- cuore -->
    <!-- <div class="cuore">
          <span>&hearts;</span>
        </div> -->
    <!-- <div class="sconto">-50%</div>
        <div class="sconto sosteni">Sostenibilitá</div> -->
    <!-- img in primo piano -->
    <img :src="img" :alt="title" />
    <span class="marca">{{ brand }}</span>
    <h4 class="nome">{{ nameProduct }}</h4>
    <span class="marca prezzo">14,99</span>
    <span class="marca prezzo originale">{{ price }}</span>
  </div>
</template>

<style lang="scss" scoped>
// @use "../assets/scss/partials/variables" as *;

.prodotto .nascosta {
  position: absolute;
  display: none;
  top: 0;
  right: 0;
}

/* hover */
.prodotto:hover .nascosta {
  display: block;
}

.prodotto .cuore:hover {
  color: red;
}

.prodotto {
  width: 410px;
  margin: 8px;
  position: relative;
  cursor: pointer;
}

.prodotto .cuore {
  position: absolute;
  top: 10px;
  left: 88%;
  padding: 5px 15px;

  font-size: 2rem;
  background-color: white;
  color: black;
}

.prodotto .sconto {
  position: absolute;
  bottom: 90px;
  left: 0;
  background-color: red;
  color: white;
  font-size: 0.8rem;
  padding: 5px 10px;
}

.sconto.sosteni {
  background-color: green;
  left: 50px;
}

.sconto.sosteni.singolo {
  left: 0;
}

.marca {
  font-size: 0.8rem;
  padding-bottom: 0;
}

.marca.prezzo {
  color: red;
}

.marca.prezzo.originale {
  color: black;
  text-decoration: line-through;
}

.prezzo::after {
  content: " \20AC";
}
.nome {
  text-transform: uppercase;
}
</style>
