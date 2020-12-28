<template>
<v-col>
  <v-card elevation="5" >
    <v-img class="mx-auto" max-width="200px" max-height="200px" padding="100px" src="https://upload.wikimedia.org/wikipedia/commons/4/46/Bitcoin.svg"></v-img>
    <v-card-title class=justify-center>{{cryptoData.code}}</v-card-title>
    <v-card-title class=justify-center>{{cryptoData.description}}</v-card-title>
    <v-card-title v-if="cryptoData.code === 'USD'" class=justify-center>${{cryptoData.rate}}</v-card-title>
    <v-card-title v-else-if="cryptoData.code === 'GBP'" class=justify-center>£{{cryptoData.rate}}</v-card-title>
    <v-card-title v-else-if="cryptoData.code === 'EUR'" class=justify-center>€{{cryptoData.rate}}</v-card-title>
</v-card>
</v-col>

</template>

<style>

</style>

<script>

export default {
  props: {
    cryptoData: {
      type: Object,
      required: true
    }
  },

  data () {
    return {
      
    }
  },

  mounted () {
  }
}
</script>
