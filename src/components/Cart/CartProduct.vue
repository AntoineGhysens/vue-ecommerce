<script setup lang="ts">
    import type { ProductInterface } from '@/interfaces/product.interface';

    defineProps<{
        product: ProductInterface
    }>()
</script>

<template>
       <div class="flex items-center p-3 bg-gray-1 border-custom">
           <strong>{{ product.title }}</strong>
           <span class="ml-4">{{ product.price }}€</span>
           <button class="ml-auto btn btn-danger flex-end justify-self-end">Supprimer</button>
       </div>
       
</template>

<style lang="scss" scoped>
</style>