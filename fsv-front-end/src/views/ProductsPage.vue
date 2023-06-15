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
    try {
      const response = await axios.get('/api/products');
      this.products = response.data;
    } catch (error) {
      console.error("Error retrieving products:", error);
      this.error = error.response && error.response.data && error.response.data.error
        ? error.response.data.error.message
        : "An error occurred while retrieving products.";
    }
  },
};
</script>
 

