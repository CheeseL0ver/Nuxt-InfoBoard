<template>
  <v-col>
    <v-card elevation="5" >
      <v-card-title class=justify-center>{{this.day}}</v-card-title>
      <v-card-title class=justify-center>{{this.date}}</v-card-title>
      <v-img v-if="weatherData.weather === 'cloudy'" src="https://www.amcharts.com/wp-content/themes/amcharts4/css/img/icons/weather/animated/cloudy.svg" ></v-img>
      <v-img v-else-if="weatherData.weather === 'pcloudy'" src="https://www.amcharts.com/wp-content/themes/amcharts4/css/img/icons/weather/animated/cloudy-day-1.svg" ></v-img>
      <v-img v-else-if="weatherData.weather === 'clear'" src="https://www.amcharts.com/wp-content/themes/amcharts4/css/img/icons/weather/animated/day.svg" ></v-img>
      <v-img v-else-if="weatherData.weather === 'lightrain'" src="https://www.amcharts.com/wp-content/themes/amcharts4/css/img/icons/weather/animated/rainy-4.svg" ></v-img>
      <v-img v-else-if="weatherData.weather === 'mcloudy'" src="https://www.amcharts.com/wp-content/themes/amcharts4/css/img/icons/weather/animated/cloudy.svg" ></v-img>
      <v-img v-else-if="weatherData.weather === 'rain'" src="https://www.amcharts.com/wp-content/themes/amcharts4/css/img/icons/weather/animated/rainy-5.svg" ></v-img>
      <v-card-text class=text-center>{{weatherData.weather}}</v-card-text>
      <v-card-text class=text-center>Hi: {{weatherData.temp2m.max}}</v-card-text>
      <v-card-text class=text-center>Low: {{weatherData.temp2m.min}}</v-card-text>
    </v-card>
  </v-col>

</template>

<style>

</style>

<script>
import parse from 'date-fns/parse';
import getDay from 'date-fns/getDay';
import format from 'date-fns/format';

export default {
  props: {
    weatherData: {
      type: Object,
      required: true
    }
  },

  data () {
    return {
      day: null,
      date: null,
      month: null
    }
  },

  mounted () {
    this.day = format(parse(this.weatherData.date, 'yyyyMMdd', new Date()), 'EEEE');
    this.date = format(parse(this.weatherData.date, 'yyyyMMdd', new Date()), "do");
    // console.log(this.weatherData);
  },
}
</script>
