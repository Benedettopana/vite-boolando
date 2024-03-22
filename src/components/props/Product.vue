<script>
export default {
  props: {
    img: String,
    subtitle: String,
    title: String,
    subPriceSale: String,
  },
  // created() {
  //   this.subtitle = "products.brand";
  // },
  mounted() {},
};
</script>

<template>
  <div class="prodotto">
    <img :src="img" alt="{{ title }}" />
    <span class="marca">{{ subtitle }}</span>
    <h4 class="nome">{{ title }}</h4>
  </div>
</template>

<style lang="scss" scoped></style>
