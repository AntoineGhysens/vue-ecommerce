<script setup lang="ts">
    import type { ProductInterface } from "@/interfaces/product.interface";
    import CartProductList from "./CartProductList.vue";

    defineProps<{
        cart: ProductInterface[]
    }>()
</script>

<template>
        <div class="p-4">
            <h1>Cart</h1>
            <CartProductList :cart="cart" />
        </div>
</template>

<style scoped>
</style>