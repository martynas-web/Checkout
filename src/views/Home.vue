<template>
  <b-container id="app">
    <b-row>
      <b-col cols="7"><Products v-bind:products="products"/></b-col>
      <b-col cols="5"><Payment/></b-col>
    </b-row>
  </b-container>
</template>

<script>
import Products from "../components/Products";
import Payment from "../components/Payment";
import axios from 'axios';

export default {
  name: "Home",
  components: {
    Products,
    Payment
  },
  data() {
    return {
      products: [ ]
    }
  },
  methods: {
  },
  created() {
    axios.get('static/products.json')
    .then(res => this.products = res.data)
  }
};
</script>

<style>
#app {
  background-color: #F7F7F7;
}
</style>
