<script setup>
const props = defineProps({
  product: {
    type: Object,
    required: true
  }
})

const emit = defineEmits([
  'add-to-cart',
  'delete-product'
])
</script>

<template>
  <div class="product">

    <h3>{{ props.product.name }}</h3>

    <p>Category: {{ props.product.category }}</p>

    <p>Price: ${{ props.product.price }}</p>

    <p>Stock: {{ props.product.stock }}</p>

    <button class="cart"
      @click="emit('add-to-cart', props.product)"
      :disabled="props.product.stock <= 0"
    >
      Add to Cart
    </button>

    <button class="btn"
      @click="emit('delete-product', props.product.id)"
    >
      Delete
    </button>

  </div>
</template>
<style>
.product{
 color: blueviolet;
 
}
.product:hover{
  color: rgb(0, 123, 255);
}
.cart{
  color: blueviolet;
  
  border-radius: 5px;
  display: inline-block;
  gap: 10px;
}
.btn{
  color:red;
  gap: 10px;
  border-radius: 4px;
  margin-left: 10px;
}


</style>