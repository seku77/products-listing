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
* {
  box-sizing: border-box;
}
body {
  margin: 0;
}
</style>
