<template>
    <div class="flex flex-col product">
        <img src="../../assets/16x9-Ratio-Image-placeholder.jpg" alt="Product ipsum" width="240" srcset="" class="product-image m-auto">
        <div class="p-2.5 flew flex-col">
            <h2>Product ipsum</h2>
            <p class="">On the other hand, we denounce with righteous indignation and dislike men who are so beguiled</p>
            <div class="flex flex-row items-center">
                <strong class="flex-auto">Prix : 1000€</strong>
                <button>Ajouter au panier</button>
            </div>
        </div>
        
    </div>
</template>



<script setup lang="ts">
</script>



<style lang="scss" scoped>
.product {
  background-color: #ffffff;
  border: var(--border);
  border-radius: var(--border-radius);
  &-image {
    border-top-right-radius: var(--border-radius);
    border-top-left-radius: var(--border-radius);
    aspect-ratio: 16/9;
    object-fit: cover;
    object-position: center;
  }
}
</style>