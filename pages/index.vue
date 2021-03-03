<template>
  <div class="container">
    <div v-if="error">
      {{ error }}
    </div>
    <ul v-else>
      <li v-for="restaurant in restaurants" :key="restaurant.id">
        {{ restaurant.name }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      restaurants: [],
      error: null,
    }
  },
  async mounted() {
    try {
      this.restaurants = await this.$strapi.$restaurants.find()
    } catch (error) {
      this.error = error
    }
  },
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>
