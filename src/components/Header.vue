
<script setup>
defineProps({
  cartCount: Number
})
</script>

<template>
  <header class="header">
    <h1>My Store</h1>
    <div class="cart-count">
      Cart: {{ cartCount }}
    </div>
  </header>
</template>
<style>
.header{
  color: rgb(197, 125, 16);
  font-size: 20px;
}
.header:hover{
  color: black;
}

</style>
