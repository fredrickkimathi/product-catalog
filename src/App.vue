<template>
  <div id="app">
    <ProductList>
      <template #header> <h1>Welcome to Our Product Catalog!</h1>
      </template>
    </ProductList>
  </div>
</template>

<script>
import ProductList from './components/ProductList.vue';

export default {
  components: {
    ProductList
  }
};
</script>

<style>
  #app {
    /* Styles for the application */
  }
</style>