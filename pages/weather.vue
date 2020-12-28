<template>
  <Nuxt />
</template>

<script>
import WeatherCard from '~/components/WeatherCard.vue'

export default {
  layout: 'weather',
  components: {
    WeatherCard
  }
}
</script>
