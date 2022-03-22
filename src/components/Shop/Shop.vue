<script setup lang="ts">
    import type { ProductInterface } from '@/interfaces/product.interface';
    import ShopProductList from './ShopProductList.vue'


    defineProps<{
        products: ProductInterface[]
    }>()

    const emit = defineEmits<{
        (e: 'addToCart', productId: number): void
    }>()
</script>

<template>
    <div>
        <ShopProductList @add-to-cart="emit('addToCart', $event)" :products="products" />
    </div>    
</template>

<style scoped>
</style>
