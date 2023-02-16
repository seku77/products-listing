<template>
  <div class="productsList">
    <div class="productOfADay">
      <h1>Product Of A Day</h1>
      <ProductCard
        v-if="products.productOfADay"
        :product="products.productOfADay"
      />
    </div>
    <ProductsSection :products="products.bestSales" title="Best Sales" />
    <ProductsSection
      :products="products.recommendedForYou"
      title="Recommended For You"
    />
  </div>
</template>

<script>
import ProductCard from "./ProductCard.vue";
import ProductsSection from "./ProductsSection.vue";
export default {
  name: "ProductsComponent",
  data() {
    return {
      products: {},
    };
  },
  components: {
    ProductsSection,
    ProductCard,
  },
  created() {
    this.getProducts();
  },
  methods: {
    async getProducts() {
      await fetch("http://localhost:8082/products", {
        method: "GET",
      })
        .then((response) => response.json())
        .then((result) => {
          this.products = result;
        })
        .catch((error) => {
          console.error("Error:", error);
        });
    },
  },
};
</script>
<style>
.productsList {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 32px 0;
  gap: 26px;
}
.productOfADay {
  display: flex;
  flex-direction: column;
}
</style>
