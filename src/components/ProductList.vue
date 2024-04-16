<template>
  <div class="product-list">
    <h2>Add Products</h2>
    <form @submit.prevent="addProduct">
      <label for="name">Product Name:</label>
      <input type="text" id="name" v-model="newProduct.name" required />
      <br />
      <label for="price">Price:</label>
      <input type="number" id="price" v-model.number="newProduct.price" required />
      <br />
      <button class="btn" type="submit">Add Product</button>
    </form>
    <ul>
      <li v-for="product in products" :key="product.id">
        {{ product.name }} - ${{ product.price | currency }}
        <button @click="removeProduct(product.id)">Remove</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      products: [],
      newProduct: {
        name: '',
        price: 0
      }
    };
  },
  methods: {
    addProduct() {
      const newId = this.products.length ? Math.max(...this.products.map(p => p.id)) + 1 : 1;
      this.products.push({ id: newId, ...this.newProduct });
      this.newProduct.name = '';  // Clear input fields after adding
      this.newProduct.price = 0;
    },
    removeProduct(id) {
      const productIndex = this.products.findIndex(p => p.id === id);
      if (productIndex > -1) {
        this.products.splice(productIndex, 1);
      }
    }
  }
};
</script>

<style scoped>
.btn:hover{
background-color: green;
}

.product-list{
text-align: center;
border: 1px;
}

</style>