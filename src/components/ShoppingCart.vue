<script setup>
const props = defineProps({
  cart: {
    type: Array,
    default: () => []
  }
})

const emit = defineEmits([
  'increase',
  'decrease',
  'remove'
])
</script>

<template>
  <section class="section">
    <h2>Shopping Cart</h2>

    <div
      v-if="props.cart.length === 0"
      class="empty"
    >
      Your cart is empty.
    </div>

    <div
      v-for="item in props.cart"
      :key="item.id"
      class="cart-item"
    >

      <div>
        <h3>{{ item.name }}</h3>

        <p>
          ${{ item.price.toFixed(2) }}
        </p>
      </div>

      <div class="quantity">

        <button
          @click="emit('decrease', item)"
        >
          -
        </button>

        <span>
          {{ item.quantity }}
        </span>

        <button
          @click="emit('increase', item)"
        >
          +
        </button>

      </div>

      <strong>
        ${{ (item.price * item.quantity).toFixed(2) }}
      </strong>

      <button style="color: blueviolet;border-radius: 5px;margin-left: 10px; margin-top: 20px;  "
        
        @click="emit('remove', item.id)"
      >
        Remove
      </button>

    </div>
  </section>
</template>
<style>
 
.quantity {
   display: flex; 
  align-items: center;
  gap: 5px;
  border-radius: 3px;
}



</style>