<template>
<div class="wrapper">
  <div class="products">
    <div class="product" v-for="product in products" :key="product.id">
      <div class="info">
        <h1>{{product.name}}

        </h1>
        <p>{{product.country}}</p>
      </div>
      <div class="image">
        <img :src="'/images/products/'+product.image">
      </div>
      <div class="price">
        <h2>{{product.price}}</h2>
        <button class="auto" @click="removeFromCart(product.id)">Remove</button>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'CartList',
  props: {
    products: Array
  },
  methods: {
      removeFromCart(product) {
        var index = this.$root.$data.cart.indexOf(product);
        this.$root.$data.cart.splice(index);
      }
  }
}

</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.products {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.product {
  margin: 10px;
  margin-top: 50px;
  width: 200px;
}

.product img {
  border: 2px solid #333;
  height: 250px;
  width: 200px;
  object-fit: cover;
}

.product .image {
  display: flex;
  justify-content: center;
  margin-bottom: 5px;
}

.info {
  background: #90EE90;
  color: #000;
  padding: 10px 30px;
  height: 80px;
}

.info h1 {
  font-size: 16px;
}

.info h2 {
  font-size: 14px;
}

.info p {
  margin: 0px;
  font-size: 10px;
}


.price {
  display: flex;
}

button {
  height: 50px;
  background: #000;
  color: white;
  border: none;
}

.auto {
  margin-left: auto;
}
/*
.footer {
  text-align: left;
  background-color: #E3BF6A;
  padding-top: 10px;
  bottom: 0px;
  width: 100%;
  position: fixed;
  height: 50px;
}

.footer-button a {
  color: #000;
  font-weight: bold;
  font-size: 18px;
  padding: 5px;
  text-align: center;
  border-radius: 10px;
  margin-left: 10px;
}

.footer-button a:hover {
  color: #000;
  background-color: #89CFF0;
  font-size: 18px;
  font-weight: bold;
  text-decoration: none;
  padding: 5px;
  border: 2px solid #89CFF0;
}*/
</style>
