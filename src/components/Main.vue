<script>
// mi import il db e le cards
import dbProducs from "../assets/data/db.json";
import Product from "./props/Product.vue";

export default {
  components: { Product },
  data() {
    return {
      dbProducs,
      products: [
        {
          image: "`../assets/img/${dbProducts.frontImage}`",
          marca: "Levi's",
          nome: "RELAXED FIT TEE UNISEX",
          prezzo: "14,99",
          prezzoOriginale: "29,99",
        },
      ],
    };
  },
};
</script>

<template>
  <div>
    Boolando Card
    <Product
      v-for="(item, index) in products"
      :key="`n-${index}`"
      :img="item.image"
      :subtitle="item.marca"
      :title="item.nome"
      :subPriceSale="item.prezzo"
    />
  </div>
</template>

<style lang="scss" scoped></style>
