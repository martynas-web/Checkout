<template>
  <div class="product-item mb-2" v-bind:class="{'is-complete':product.completed}">
    <div>
        <b-card class="product-item-card" header-tag="header" footer-tag="footer">
          <template class="card-header" #header>
            <b-row align-h="start">
              <b-col cols="4">
                <p class="card-title mb-0">{{product.quantity}}x {{product.title}}</p>
              </b-col>
              <b-col class="pr-0" cols="12" md="auto">
                <p class="card-title discount-number mb-0 p-1">Save {{product.discount}}%</p>
              </b-col>
              <b-col cols="12" md="auto">
                <div v-if="product.bestSeller == true" >
                <p class="card-title best-seller mb-0 p-1">Best Seller</p>
                </div>
              </b-col>
               <b-col cols="12" md="auto">
                <div v-if="product.fastDelivery == true" >
                <p class="card-title mb-0 p-1">Fast delivery</p>
                </div>
              </b-col>
            </b-row>
          </template>
          <b-row >
            <b-col cols="7">
              <div class="product-quantity-images">
              <div class="product-image"  v-for="index in parseInt(product.quantity)" :key="index">
              <b-img width="130px" :src="product.imageUrl" />
              </div>
              </div>
            </b-col>
            <b-col cols="5">
              <p class="mb-0"><span class="product-price-each">${{price = (product.priceEach * (100 - product.discount) / 100).toFixed(2)}}</span> /each</p>
              <hr class="my-1">
              <p class="mb-0">Original: <span class="text-red">${{product.priceEach}}</span></p>
              <p class="mb-0">Total: ${{(price * product.quantity).toFixed(2)}}</p>
            </b-col>
          </b-row>
          <template class="card-footer" #footer>
            <b-row align-h="start">
            <b-col cols="3">
                <p class="card-title mb-0">Sell out risk: <span class="text-red">{{product.sellOutRisk}}</span></p>
              </b-col>
              <b-col cols="3">
                 <div v-if="product.fastDelivery == true" >
                <p class="text-green card-title mb-0">Fast delivery</p>
                </div>
              </b-col>
              <b-col cols="3">
                <p class="card-title mb-0">Discount: {{product.discount}}%</p>
              </b-col>
              <b-col cols="3">
                <p class="card-title mb-0">{{product.productPopularity}}</p>
              </b-col>
            </b-row>
          </template>
        </b-card>
    </div>
  </div>
</template>
<script>
export default {
  name: "ProductItem",
  props: ["product"],
  methods: {
    markComplete() {
      this.product.completed = !this.product.completed;
    }
  }
};
</script>
<style scoped>

.card-header {
  background-color: rgb(146 146 146);
}

.card-header p {
  color: white;
}

.product-price-each {
  font-size: 40px;
}

.best-seller {
  border-radius: 0.25rem;
  background-color: #cc0000;
}

.discount-number {
  background-color: #44B787;
  border-radius: 0.25rem;
}

.card-footer {
  background-color: transparent;
}

.card-footer p {
  font-size: 12px;
}

.text-red {
  color:#cc0000;
}

.text-green {
  color: #44B787;
}

.product-quantity-images {
  display: inline-flex;
}

.product-quantity-images .product-image:not(:first-child) {
   margin-left: -60px;
}

</style>