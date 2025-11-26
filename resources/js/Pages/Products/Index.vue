<script setup>
defineProps({
  products: {
    type: Array,
    required: true,
  },
});
</script>

<template>
  <div class="container">
    <h1>Каталог товаров</h1>
    <div class="grid">
      <article
        v-for="product in products"
        :key="product.id"
        class="card"
      >
        <img
          class="card-image"
          :src="product.image_path"
          :alt="product.title"
        />
        <h2 class="card-title">{{ product.title }}</h2>
        <p class="card-price">{{ product.price }} ₽</p>
        <p class="card-stock">
          На складе: {{ product.stock }} шт.
        </p>
      </article>
    </div>
  </div>
</template>

<style scoped>
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
  font-family: Arial, sans-serif;
}

h1 {
  text-align: center;
  margin-bottom: 30px;
  color: #333;
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 20px;
}

.card {
  border: 1px solid #ddd;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  transition: transform 0.2s, box-shadow 0.2s;
  background-color: #fff;
}

.card-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.card-title {
  font-size: 1.2em;
  margin: 15px;
  color: #333;
}

.card-price {
  font-size: 1.1em;
  font-weight: bold;
  color: #e74c3c;
  margin: 0 15px;
}

.card-stock {
  font-size: 0.9em;
  color: #666;
  margin: 0 15px 15px;
}
</style>