<template>
    <div v-if="products.length > 0">
    <ProductsListItem
    v-for="product in products"
    :key="product.id"
    :product="product"/>
</div>
<p v-else>Your cart is empty</p>
</template>

<script>
import ProductsListItem from './ProductsListItem.vue'
export default {
    name: 'ProductsList',
    props: ['products'],
    components: {
        ProductsListItem,
    },
}
</script>