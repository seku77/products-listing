<template>
  <div class="row badges">
    <div
      class="badge"
      v-for="[badge, index] in badges"
      :key="index"
      :class="badge"
    ></div>
  </div>
</template>

<script>
export default {
  name: "ProductBadges",
  props: {
    badges: {
      type: Array,
    },
  },
};
</script>
