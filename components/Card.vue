<template>
  <div class="card">
    <div>{{ card.serviceName }}</div>
    <div>{{ card.businessName }}</div>
    <div>
      <span
        v-for="i in card.serviceRating"
        :key="i"
        class="fa-solid fa-star"
      ></span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    card: Object,
  },
}
</script>

<style scoped>
.card {
  border: 1px solid #ccc;
  padding: 10px;
  margin: 10px;
}
</style>
