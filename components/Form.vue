<template>
  <form @submit.prevent="submitForm">
    <label for="name">Service Name </label>
    <input
      v-model="serviceName"
      type="text"
      placeholder="Type Service Name"
      id="name"
    />
    <label for="business">Business Name</label>
    <input
      v-model="businessName"
      type="text"
      placeholder="Type Business Name"
      id="business"
    />
    <label for="rating">Rate Service</label>
    <input
      v-model.number="serviceRating"
      type="number"
      placeholder="Service Rating"
      id="rating"
    />
    <button type="submit">Details</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      serviceName: '',
      businessName: '',
      serviceRating: null,
    }
  },
  methods: {
    submitForm() {
      this.$emit('formSubmitted', {
        serviceName: this.serviceName,
        businessName: this.businessName,
        serviceRating: this.serviceRating,
      })
      this.resetForm()
    },
    resetForm() {
      this.serviceName = ''
      this.businessName = ''
      this.serviceRating = null
    },
  },
}
</script>
