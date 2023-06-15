<template>
  <div id="page-wrap">
<ProductsGrid :products="products"/>
  </div>
</template>

<script>

import ProductsGrid from "../components/ProductsGrid.vue";
import axios from 'axios'
export default {
  name: "ProductsPage",
  components: {ProductsGrid},
  data() {
    return {
      products: [],
    };
  },
  async created() {
    const result = await axios.get('/api/products')
    this.products = result.data
  }
};
</script>


