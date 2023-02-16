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
.badges {
  display: flex;
  gap: 8px;
}
.badge {
  height: 24px;
  width: 24px;
  background-repeat: no-repeat;
  background-position: center;
  &.new {
    background-image: url("./assets/icons/new.svg");
  }
  &.collectionSale {
    background-image: url("./assets/icons/tag.svg");
  }
  &.lastItems {
    background-image: url("./assets/icons/cart-exclamation.svg");
  }
  &.ratingStar {
    background-image: url("./assets/icons/star.svg");
  }
}
</style>
