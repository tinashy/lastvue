<template>
  <div id="app">
    <div class="row">
      <div class="col-md-7">
        <div class="row">
          <div class="col-md-6" v-for="product in products" :key="product.id">
            <product :isInCart="isInCart(product)" v-on:add-to-cart="addToCart(product)" :product="product" />
          </div>
        </div>
      </div>
      <div class="col-md-5"></div>
    </div>
  </div>
</template>

<script>
import Product from './components/Product.vue'
import products from './products.json'

export default {
  name: 'app',
  components: {
    Product
  },
  data() {
    return {
      products,
      cart: []
    }
  },
  methods: {
    addToCart(product) {
      this.cart.push(product)
    },
    isInCart(product) {
      const item = this.cart.find(item => item.id === product.id)
      if(item) {
        return true
      }
      return false
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
