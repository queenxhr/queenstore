<template>
  <div>
    <div id="page-wrap">
      <h1>Product</h1>
      <p>This is the product index page.</p>
      <div class="grid-wrap">
        <div class="product-item" v-for="product in products" :key="product.id">
            <img :src="product.imageUrl" alt="Product Image" />
            <h2 class="product-name">{{ product.name }}</h2>
            <p class="product-price">Rp{{ product.price }}</p>
            <router-link>Add to Cart</router-link>
            <router-link
              :to="{ name: 'product-detail', params: { id: product.index } }"
            >
              <button>View Detail</button>
            </router-link>
          <!-- <a :href="'/product/' + product.id">
          </a> -->
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { products } from "../../data-seed";
export default {
  data() {
    return {
      products,
    };
  },
};
</script>

<style scoped>
.grid-wrap {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  margin-top: 16px;
}

.product-item {
  align-items: center;
  border-radius: 8px;
  box-shadow: 0px 2px 5px #888;
  display: flex;
  flex-direction: column;
  margin-bottom: 2%;
  padding: 20px;
  position: relative;
  width: 32%;
}

.product-name {
  margin-bottom: 0;
}

img {
  height: 200px;
  width: 200px;
  border-radius: 5%;
}

a {
  width: 100%;
}

button {
  width: 100%;
}
</style>
