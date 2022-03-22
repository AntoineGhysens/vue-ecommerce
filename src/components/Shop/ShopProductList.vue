<script setup lang="ts">
    import type { ProductInterface } from '@/interfaces/product.interface';
    import ShopProduct from "./ShopProduct.vue";
    
    defineProps<{
        products: ProductInterface[]
    }>()

    const emit = defineEmits<{
        (e: 'addToCart', productId: number): void
    }>()
</script>

<template>
    <ul class="grid gap-[20px]" >
        <ShopProduct class="p-5 rounded" @add-to-cart="emit('addToCart', $event)" v-for="product of products" :product="product" />
    </ul>
</template>

<style scoped>
    .grid {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr 1fr;
    }
</style>