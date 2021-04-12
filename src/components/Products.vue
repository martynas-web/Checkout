<template>
  <div class="products-list p-3">
    <div class="product-info">
    <img src="../assets/order quantity.svg" alt=""><p class="mb-0 pl-3">Select your order quantity</p>
    </div>
    <hr class="my-3">
    <div v-for="product in products" v-bind:key="product.id">
      <ProductItem v-bind:product="product" v-on:del-product="$emit('del-product', product.id)"/>
    </div>
  </div>
</template>

<script>
import ProductItem from './ProductItem.vue';
export default {
  name: "Products",
  components: {
    ProductItem
  },
  props: ["products"]
};
</script>
<style scoped>
.products-list {
  background-color: white;
  border-radius: 0.25rem;
}

.product-info {
  display: inline-flex;
}
</style>
