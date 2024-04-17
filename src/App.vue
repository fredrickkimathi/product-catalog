<template>
  <div id="app">
    <ProductList>
      <template id="welcome"> <h1>Welcome to Our Product Catalog!</h1>
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
    border: 1px solid gray;
    margin: 100px;
    background-color: cyan;
  }
  #welcome {
  padding: 20px;
  }
</style>