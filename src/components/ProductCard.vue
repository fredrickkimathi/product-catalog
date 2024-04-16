<template>
  <div class="product-card">
    <img :src="product.image" alt="Product Image">
    <h3>{{ product.name }}</h3>
    <p>{{ product.price | currency }}</p>
    <button @click="$emit('add-product', product)">Add to Cart</button>
  </div>
</template>

<script>
export default {
  props: {
    product: Object
  },
  methods: {
    addProduct(product) {
      this.$emit('add-product', product); // Emit the event with product data
    }
  }
};
</script>

<style scoped>
  .product-card {
    /* Styles for the product card */
  }
</style>