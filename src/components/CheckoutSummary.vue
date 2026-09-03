<script setup>
const props = defineProps({
  subtotal: Number,
  discountRate: Number,
  discount: Number,
  grandTotal: Number,
  promoCode: String,
  cartLength: Number
})

const emit = defineEmits([
  'update-promo'
])
</script>

<template>
  <section class="checkout">

    <h2 style="color:darkseagreen;">Checkout Summary</h2>

    <input
      :value="props.promoCode"
      @input="
        emit(
          'update-promo',
          $event.target.value
        )
      "
      type="text"
      placeholder="Promo Code: SAVE20"
    />


    <div class="summary">
      <br>

      <div>
        <span>ទឹកប្រាក់ត្រូវបង់:</span>

        <strong>
          ${{ props.subtotal.toFixed(2) }}
        </strong>
      </div>

      <hr />

       

      </div>  

   

    

  </section>
</template>

