<template>
  <div id="app">
    <div class="row">
      <div class="col-md-8">
        <div class="row">
          <div class="col-md-6" v-for="product in products" :key="product.id">
            <Product :is-in-cart="isInCart(product)" @add-to-cart="addToCart(product)" :product="product" />
            <!-- always use kebab case for html attribs -->
          </div>
        </div>
      </div>
      <div class="col-md-4">
        <div class="row">
          <div class="col">
            <Cart v-on:pay="pay" v-on:remove-from-cart="removeFromCart($event)" :items="cart" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Product from './components/Product.vue'
import products from './products.json'
import Cart from './components/Cart.vue'

export default {
  name: 'app',
  components: {
    Product,
    Cart
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
    },
    removeFromCart(product) {
      this.cart = this.cart.filter(item => item.id !== product.id)
    },
    pay() {
      this.cart = []
      alert('Shopping Completed!')
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-top: 60px;
}
</style>
