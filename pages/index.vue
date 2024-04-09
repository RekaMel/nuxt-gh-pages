<template>
  <div>
    <Form @formSubmitted="addCard" />
    <div class="flex-container">
      <Card v-for="(card, index) in cards" :key="index" :card="card" />
    </div>
    <nuxt-link to="/experience">Experience Page</nuxt-link>
  </div>
</template>

<script>
import Form from '~/components/Form.vue'
import Card from '~/components/Card.vue'

export default {
  components: {
    Form,
    Card,
  },
  data() {
    return {
      cards: [],
    }
  },
  methods: {
    addCard(card) {
      this.cards.push(card)
    },
  },
}
</script>

<style>
.flex-container {
  display: flex;
  flex-wrap: wrap;
}
</style>
