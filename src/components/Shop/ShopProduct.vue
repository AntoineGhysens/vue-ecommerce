<script setup lang="ts">
  import type { ProductInterface } from '@/interfaces/product.interface';

  defineProps<{
    product: ProductInterface
  }>()

  const emit = defineEmits<{
        (e: 'addToCart', productId: number): void
    }>()
</script>

<template>
    <div class="flex flex-col product">
        <img :src=" product.image ? '' : `src/assets/images/16x9-Ratio-Image-placeholder.jpg`" alt="Product ipsum" width="240" srcset="" class="m-auto product-image">
        <div class="p-2.5 flew flex-col">
            <h2> {{product.title }}</h2>
            <p class="pb-4">{{ product.description }}</p>
            <div class="flex flex-row items-center">
                <strong class="flex-auto">Prix : {{ product.price }}€</strong>
                <button @click="emit('addToCart', product.id)" class="btn btn-primary">Ajouter au panier</button>
            </div>
        </div>
        
    </div>
</template>

<style lang="scss" scoped>
.product {
  background-color: #ffffff;
  border: var(--border);
  border-radius: var(--border-radius);
  // max-height: 25rem;
  &-image {
    border-top-right-radius: var(--border-radius);
    border-top-left-radius: var(--border-radius);
    aspect-ratio: 16/9;
    object-fit: cover;
    object-position: center;
  }
}
</style>