<template>
  <div class="product">
    <div class="productImage">
      <img :src="product.image" :alt="product.name + 'Image'" />
    </div>
    <h2>{{ product.name }}</h2>
    <div class="details">
      <div class="row">In stock: {{ product.amount }}</div>
      <div v-if="product.addedToWishlist" class="row">Added to wish list</div>
      <div class="row badges">
        <div
          class="badge"
          v-for="(value, name, index) of product.badges"
          :key="index"
        >
          <label v-if="value === true">{{ name }}</label>
        </div>
      </div>
      <div class="price">${{ product.price.current }}</div>
      <div class="rating">Rating: {{ product.rating }}</div>
      <div class="addToCart">Add to cart</div>
    </div>
  </div>
</template>
<script>
export default {
  name: "ProductCard",
  props: {
    product: {
      type: Object,
    },
  },
};
</script>

<style lang="scss">
.product {
  display: flex;
  flex-direction: column;
  align-items: center;
  border-radius: 8px;
  background-color: #fff;
  box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
  overflow: hidden;
}
.addToCart {
  background-color: blue;
  padding: 8px 16px;
  border-radius: 8px;
  color: #fff;
  font-weight: 600;
  width: 50%;
}
.details {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  padding: 8px;
  .price {
    font-weight: 600;
  }
}
</style>
