<template>
<div>
  <h1> Your Cart </h1>
  <div v-if="this.$root.$data.cart.length == 0">
    <p>Your cart is empty!</p>
  </div>
  <div v-else>
    <CartList :products="cart" />
  </div>
</div>
</template>

<script>
import CartList from "../components/CartList.vue"
export default {
  name: 'Browse',
  components: {
    CartList
  },
  data() {
    return {
    }
  },
  computed: {
    cart() {
      return this.$root.$data.cart;
    }
  },
};
</script>
