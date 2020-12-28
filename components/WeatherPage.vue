<template>
    <v-container>
        <v-row class="text-xs-1 text-center">
                <v-col>
                <h1 class="text-center">{{new Intl.DateTimeFormat('en-US', {month: 'long'}).format(new Date())}}</h1>
                </v-col>
            </v-row>
                
            <v-row>
                <WeatherCard
                v-for="entry in weatherData"
                :key="entry.min"
                :weatherData="entry"
            />
            </v-row>
    </v-container>
</template>

<style>

</style>

<script>
import axios from 'axios';
import WeatherCard from './WeatherCard.vue';

export default {

  data () {
    return {
      name: 'ShandonCodes',
      weatherData: null
    }
  },

  mounted () {
    axios
      .get('http://www.7timer.info/bin/civillight.php?lon=-78.825562&lat=35.823483&ac=0&unit=British&output=json&tzshift=0')
      .then(res => (this.weatherData = res.data.dataseries))
  },
  
  methods: {
    updateValues: function () {
      setInterval(function () {
        console.log('UPDATING Weather!!!')
        axios
      .get('http://www.7timer.info/bin/civillight.php?lon=-78.825562&lat=35.823483&ac=0&unit=British&output=json&tzshift=0')
      .then(res => (this.weatherData = res.data.dataseries))
      }.bind(this), 15000);
    }
  },

  created: function () {
    this.updateValues();
  }
}
</script>
