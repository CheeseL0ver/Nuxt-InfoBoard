<template>
    <v-container>
            <v-row>
                <CryptoCard
                v-for="currency in cryptoData"
                :key="currency.code"
                :cryptoData="currency"
            />
            </v-row>
    </v-container>
</template>

<style>

</style>

<script>
import axios from 'axios';
import CryptoCard from './CryptoCard';

export default {

  data () {
    return {
        cryptoData: null
    }
  },

  mounted () {
    axios
      .get('https://api.coindesk.com/v1/bpi/currentprice.json')
      .then(res => (this.cryptoData = res.data.bpi))
  },

  methods: {
    updateValues : function () {
      setInterval(function () {
        console.log('UPDATING Crypto!!!')
        axios
      .get('https://api.coindesk.com/v1/bpi/currentprice.json')
      .then(res => (this.cryptoData = res.data.bpi))
      }.bind(this), 15000);
    }
  },

  created: function (){
    this.updateValues();
  }
}
</script>
