<script setup>
const props = defineProps({
  newProduct: Object
})

const emit = defineEmits(['add-product'])
</script>

<template>
  <section class="section">
    <h2>Add Product</h2>

    <form
      class="product-form"
      @submit.prevent="emit('add-product')"
    >
      <input
        v-model="props.newProduct.name"
        type="text"
        placeholder="Product name"
      />

      <select v-model="props.newProduct.category">
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

      <input
        v-model.number="props.newProduct.price"
        type="number"
        min="0"
        placeholder="តម្លៃ$"
      />

      <input
        v-model.number="props.newProduct.stock"
        type="number"
        min="0"
        placeholder="Stock"
      />

      <br>
      <br>

      <button class="btn"  type="submit">
        Add Product
      </button>
    </form>
  </section>
</template>
<style>
 .section{
  color: blue;
  padding: 10px;
  margin-left: 10px;
} 
.btn{
  color:cornflowerblue;
  border-radius: 5px;
  margin-left: 5px  ;
  
}
.btn:hover{
  color: cyan;
}
input{
  margin-left: 10px;
  border-radius: 5px;
}
select{
  background-color:darksalmon;
  margin-left: 10px;
}


</style>