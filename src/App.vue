<script setup lang="ts">
  import TheHeader from './components/Header.vue'
  import TheFooter from './components/Footer.vue'
  import Shop from './components/Shop/Shop.vue'
  import Cart from './components/Cart/Cart.vue'
  import data from './data/product'
  import { reactive } from 'vue'
  import type { ProductInterface } from './interfaces/product.interface'

  const state = reactive<{
    products: ProductInterface[],
    cart: ProductInterface[]
  }>({
    products: data,
    cart: []
  }) 

  const addToCart = (productId: number):void => {
    const product = state.products.find(product => product.id === productId)
    if (product?.id == productId && !state.cart.find(product => product.id == productId)) {
      state.cart.push({...product})
    }
  }

  const cart = "cart"
</script>

<template>
  <div class="app-container">
    <TheHeader class="header"/>
    <Shop @add-to-cart="addToCart" :products="state.products" class="p-4 shop bg-gray-2" />
    <Cart :cart="state.cart" class="cart" />
    <TheFooter class="footer" />
  </div>
</template>

<style lang="scss">   
@import './assets/debug.scss';

.app-container {
  min-height: 100vh;
  display: grid;
  grid-template-areas: "header header" "shop cart" "footer footer";
  grid-template-columns: 75% 25%;
  grid-template-rows: 48px auto 48px;
}

.header {
  grid-area: header;
}

.shop {
  grid-area: shop;
}

.cart {
  grid-area: cart;
}

.footer {
  grid-area: footer;
}
</style>