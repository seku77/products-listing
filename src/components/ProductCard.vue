<template>
  <div class="product">
    <div class="top">
      <div class="productImage">
        <img :src="product.image" :alt="product.name + 'Image'" />
      </div>
      <h2>{{ product.name }}</h2>
      <div class="details">
        <div class="detailsLeft">
          <div class="row">In stock: {{ product.amount }}</div>
          <div v-if="product.addedToWishlist" class="row">On wish list</div>
          <div class="row badges">
            <div
              class="badge"
              v-for="[badge, index] in badgesList(product.badges)"
              :key="index"
              :class="badge"
            ></div>
          </div>
        </div>
        <div class="detailsRight">
          <div
            class="regularPrice"
            v-if="product.price.regular !== product.price.current"
          >
            ${{ product.price.regular }}
          </div>
          <div class="price">${{ product.price.current }}</div>
        </div>
      </div>
    </div>
    <div class="bottom">
      <div class="badges">
        <div
          class="badge ratingStar"
          v-for="n in product.rating"
          :key="n"
        ></div>
      </div>
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
  methods: {
    badgesList(badges) {
      return Object.entries(badges).filter((badge) => badge[1] === true);
    },
  },
};
</script>

<style lang="scss">
.product {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  border-radius: 8px;
  background-color: #fff;
  box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
  overflow: hidden;
  gap: 12px;

  h2 {
    text-align: center;
  }
}
.top {
  width: 100%;
}
.bottom {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.addToCart {
  background-color: blue;
  padding: 8px 16px;
  border-radius: 8px;
  color: #fff;
  font-weight: 600;
  width: 50%;
  margin: 18px 0;
  cursor: pointer;
  text-align: center;
}
.details {
  display: flex;
  justify-content: space-between;
  width: 100%;
  padding: 0 16px;
  div {
    display: flex;
    flex-direction: column;
    gap: 4px;
  }
  .price {
    font-weight: 600;
  }
  .regularPrice {
    text-decoration: line-through;
  }
  .row {
    width: 100%;
    display: flex;
    flex-direction: row;
  }
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
    background-image: url("../assets/icons/new.svg");
  }
  &.collectionSale {
    background-image: url("../assets/icons/tag.svg");
  }
  &.lastItems {
    background-image: url("../assets/icons/cart-exclamation.svg");
  }
  &.ratingStar {
    background-image: url("../assets/icons/star.svg");
  }
}
</style>
