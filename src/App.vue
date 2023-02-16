<template>
  <ProductsComponent />
</template>

<script>
import ProductsComponent from "./components/ProductsComponent.vue";

export default {
  name: "App",
  components: {
    ProductsComponent,
  },
};
</script>

<style lang="scss">
@import "./style/global.scss";
</style>
