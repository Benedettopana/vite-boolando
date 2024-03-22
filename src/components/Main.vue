<script>
// mi import il db e le cards
import dbProducts from "../assets/data/db.json";
import Product from "./props/Product.vue";

export default {
  components: { Product },
  data() {
    return {
      dbProducts,
      // products: [
      //   {
      //     image: "`../assets/img/${dbProducts.frontImage}`",
      //     marca: "Levi's",
      //     nome: "RELAXED FIT TEE UNISEX",
      //     prezzo: "14,99",
      //     prezzoOriginale: "29,99",
      //   },
      // ],
    };
  },
  methods: {
    getImagePath(img) {
      return new URL(`../assets/img/${img}`, import.meta.url).href;
    },
  },
  mounted() {
    console.log("prodotti ", this.dbProducts.products);
  },
};
</script>

<template>
  <div>
    <h1>Prodotti</h1>
    <div class="container">
      <Product
        v-for="item in dbProducts.products"
        :key="item.id"
        :product="item"
      />
    </div>
  </div>
</template>

<style lang="scss" scoped>
// @use "../assets/scss/partials/variables" as *;
</style>
