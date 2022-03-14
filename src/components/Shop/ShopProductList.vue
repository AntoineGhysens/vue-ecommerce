<template>
    <ul class="grid" >
        <ShopProduct />
        <ShopProduct />
        <ShopProduct />
        <ShopProduct />
        <ShopProduct />
        <ShopProduct />
        <ShopProduct />
        <ShopProduct />
    </ul>
</template>

<script setup lang="ts">
import ShopProduct from "./ShopProduct.vue";
</script>

<style scoped>
    .grid {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr 1fr;
        grid-auto-rows: 300px;
    }
</style>