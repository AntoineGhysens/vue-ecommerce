<script setup lang="ts">
    import type { ProductInterface } from '@/interfaces/product.interface';
    import CartProduct from './CartProduct.vue';

    defineProps<{
        cart: ProductInterface[]
    }>()
</script>

<template>
    <div class="flex flex-col">
        <CartProduct class="cart-product" v-for="product of cart" :product="product" />
    </div>
</template>

<style lang="scss" scoped>
    .cart-product + .cart-product {
        margin-top: 1em;
    }
</style>