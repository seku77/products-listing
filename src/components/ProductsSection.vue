<template>
  <div class="section">
    <h2 class="title">{{ title }}</h2>
    <div class="products">
      <ProductCard
        v-for="(product, index) in products"
        :key="index"
        :product="product"
      />
    </div>
  </div>
</template>
<script>
import ProductCard from "./ProductCard.vue";
export default {
  data() {
    return {};
  },
  props: {
    title: {
      type: String,
    },
    products: {
      type: Array,
    },
  },
  components: {
    ProductCard,
  },
};
</script>
<style lang="scss">
.section {
  display: flex;
  flex-direction: column;
  padding: 24px;
  align-items: center;
  background-color: #f4f4f4;
  .title {
    margin-top: 0;
  }
}
.products {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  width: 100%;
  justify-content: center;
}
</style>
