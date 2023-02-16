<template>
  <div class="badges">
    <div class="badge ratingStar" v-for="n in rating" :key="n"></div>
  </div>
</template>
<script>
export default {
  props: {
    rating: {
      type: Number,
    },
  },
};
</script>
<style></style>
