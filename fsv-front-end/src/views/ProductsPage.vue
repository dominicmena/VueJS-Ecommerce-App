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
      console.error("Error retrieving products:", error.response.data);
      console.log("Error details:", error.response);
      // You can further handle the error here, such as showing an error message or taking appropriate action
    }
  },
};
</script>


