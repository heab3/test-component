
<script setup>

// import ProductCard from './component/ProductCard.vue'
// const searchQuery = ref('')
// const selectedCategory = ref('All')
// const sortBy = ref('default')
import ProductCard from './ProductCart.vue'

const props = defineProps({
  products: {
    type: Array,
    default: () => []
  }
})

const emit = defineEmits([
  'add-to-cart',
  'delete-product'
])
</script>

<template>
  <section class="section">
    <h2>Product Catalog</h2>

    <div class="filters">
      <input
        v-model="searchQuery"
        type="text"
        placeholder="Search product..."
      />

      <select v-model="selectedCategory">
        <option value="All">
          All Categories
        </option>

        <option value="Electronics">
          Electronics
        </option>

        <option value="Food">
          Food
        </option>

        <option value="Fashion">
          Fashion
        </option>
      </select>

      <select v-model="sortBy">
        <option value="default">
          តម្រៀប
        </option>

        <option value="low-high">
          Price: Low → High
        </option>

        <option value="high-low">
          Price: High → Low
        </option>
      </select>
    </div>

    <div class="product-grid">
      <ProductCard
        v-for="product in props.products"
        :key="product.id"
        :product="product"
        @add-to-cart="emit('add-to-cart', product)"
        @delete-product="emit('delete-product', product.id)"
      />
    </div>

    <p
      v-if="props.products.length === 0"
      class="empty"
    >
      No products found.
    </p>
  </section>
</template>
<style>
.section{
  color:rgb(192, 117, 24);
  gap: 10px;
}



</style>




