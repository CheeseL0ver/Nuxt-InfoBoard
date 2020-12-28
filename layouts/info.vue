<template>
  <v-app>
    
    
    <v-carousel :show-arrows="false" :cycle="true" :interval="15000" :hide-delimiters="true" :height="800">
      <v-carousel-item>
        <Crypto />
      </v-carousel-item>
      <v-carousel-item>
        <WeatherPage />
      </v-carousel-item>
    </v-carousel>
  </v-app>
</template>

<script>
// import axios from 'axios';
import WeatherPage from '../components/WeatherPage.vue';
import Crypto from '../components/Crypto.vue';

export default {

}
</script>
