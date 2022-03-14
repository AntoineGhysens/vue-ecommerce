<script setup lang="ts">
  import TheHeader from './components/Header.vue'
  import TheFooter from './components/Footer.vue'
  import Shop from './components/Shop/Shop.vue'
  import Cart from './components/Cart.vue'
</script>

<template>
  <div class="app-container">
    <TheHeader class="header"/>
    <Shop class="shop" />
    <Cart class="cart" />
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
