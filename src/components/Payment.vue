<template>
  <div class="payment-methods p-3">
    <div class="payment-info">
      <img src="../assets/safe payment.svg" alt />
      <p class="mb-0 pl-3">Payment methonds</p>
    </div>
    <hr class="my-3" />
    <b-row>
        <b-col cols="6">
            <p>Credit card</p>
        </b-col>
        <b-col cols="6">
            <img src="../assets/payments cards.png" alt="payment cards">
        </b-col>
    </b-row>
    <hr class="my-3" />
    <template>
  <div class="mb-5" id="card-check">
    <vue-c-card
      :number="cc.number"
      :holder="cc.holder"
      :exp="cc.exp"
      :cvc="cc.cvc"
      :is-typing-cvc="isTypingCvc"/>
    <b-form-input class="mb-1" type="text" placeholder="Card number" v-model="cc.number" id="number"></b-form-input>
    <b-form-input class="mb-1" type="text" placeholder="Card holder" v-model="cc.holder" id="holder"></b-form-input>
    <b-form-input class="mb-1" type="text" placeholder="Expiration date" v-model="cc.exp" id="exp"></b-form-input>
    <b-form-input class="mb-1" type="text" placeholder="CVV" v-model="cc.cvc"
      @focus="isTypingCvc = true"
      @blur="isTypingCvc = false" id="cvc"></b-form-input>
  </div>
   <div class="payment-info mb">
      <img src="../assets/person icon.svg" alt />
      <p class="mb-0 pl-3">Personal information</p>
    </div>
    <hr class="my-3" />
    <b-form-input class="mb-1" type="text" placeholder="Email Address" id="email-address"></b-form-input>
    <b-form-input class="mb-1" type="text" placeholder="First Name" id="first-name"></b-form-input>
    <b-form-input class="mb-1" type="text" placeholder="Last Name" id="last-name"></b-form-input>
    <b-form-input class="mb-1" type="text" placeholder="Phone" id="phone"></b-form-input>
    <div class="payment-info mt-4">
      <img src="../assets/shiping icon.svg" alt />
      <p class="mb-0 pl-3">Shipping information</p>
    </div>
    <hr class="my-3" />
    <b-form-input class="mb-1" type="text" placeholder="Address" id="address"></b-form-input>
    <b-form-input class="mb-1" type="text" placeholder="City" id="city"></b-form-input>
    <b-form-input class="mb-1" type="text" placeholder="Country" id="country"></b-form-input>
    <b-form-input class="mb-1" type="text" placeholder="State" id="state"></b-form-input>
    <b-form-input class="mb-1" type="text" placeholder="Zip/Postcode" id="postcode"></b-form-input>

    <b-button class="mt-4" block variant="success">Complete Purchase</b-button>
</template>
  </div>
</template>
<script>
import VueCCard from 'vue-ccard';

export default {
  name: 'app',
  components: {
    VueCCard,
  },
  data() {
    return {
      isTypingCvc: false,
      cc: {
        number: '',
        holder: '',
        exp: '',
        cvc: '',
      },
    };
  },
};
</script>
<style scoped>
.payment-methods {
  background-color: white;
  border-radius: 0.25rem;
}

.payment-info {
  display: inline-flex;
}
</style>