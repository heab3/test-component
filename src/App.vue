

///exercise 1
  <!-- <script setup>
import { ref } from 'vue'

const count = ref(0)

const increase = () => {
  count.value++
}
const decrease = () => {
  count.value--
}

const reset = () => {
  count.value = 0
}
</script> 


<template>
    <h1>Counter</h1>

    <h2>{{ count }}</h2>
    <button @click="increase">increase</button>
    <button @click="decrease">decrease</button>
    <button @click="reset">reset</button>

</template>
  -->

///exercise2

 <!-- <template>
<button @click="msg"></button>
<p v-if="isVisible">velcome vue 3</p>

<p v-else> លាក់</p>
</template>

<script setup>
import { ref } from 'vue'

const isVisible=ref(true)

const msg=()=>{
  isVisible.value=!isVisible.value
}
</script>  -->


///exercise3
<!-- <template>
  <input v-model="username" placeholder="សូមបញ្ជូលឈ្មោះរបស់អ្នក">
  <p v-if="username===''">សូមបញ្ចូលឈ្មោះរបស់អ្នក</p>
  <p v-else> សូស្ដី,{{ username }}</p>
</template>

<script>
import { ref } from 'vue'
const username=ref('')
</script>  -->





///excercise4

<!-- <script setup>
import { ref } from 'vue'

const todos=ref([
  "ទិញផ្លែឈើ", "រៀន Vue 3"

])
const newTodo = ref('')

// Function បន្ថែម Item
const addTodo = () => {
  if (newTodo.value.trim() !== '') {
    todos.value.push(newTodo.value)
    newTodo.value = ''
  }
}

// Function លុប Item
const removeTodo = (index) => {
  todos.value.splice(index, 1)
}
</script>

<template>
    <h1>បញ្ជីទំនិញត្រូវទិញ</h1>

    <input 
      v-model="newTodo"
      placeholder="បញ្ចូលទំនិញថ្មី..."
    />

    <button @click="addTodo">
      Add
    </button>
  
    <ul>
      <li v-for="(todo, index) in todos" :key="index">

        {{ todo }}

        <button @click="removeTodo(index)">
          Delete
        </button>

      </li>
    </ul>

</template> -->

///exercise5
<!-- <script setup>
import { ref, computed } from 'vue'

const num1 = ref(0)
const num2 = ref(0)

const sum = computed(() => {
  return num1.value / num2.value
})
</script>

<template>
  <div>
    <h1>Simple Adder</h1>

    <input
      v-model.number="num1"
      type="number"
      placeholder="first 1"
    />

    <input
      v-model.number="num2"
      type="number"
      placeholder="second 2"
    />

    <h2>result: {{ sum }}</h2>
  </div>
</template> -->


///exercise6
<!-- <script setup>
import { ref } from 'vue'

// Boolean State
const isDarkMode = ref(false)

// Toggle Theme
const toggleTheme = () => {
  isDarkMode.value = !isDarkMode.value
}
</script>

<template>
  <div
    class="container"
    :class="{ dark: isDarkMode }"
  >
    <h1> Theme Toggle</h1>

    <p>
      Theme បច្ចុប្បន្ន៖
      <strong>
        {{ isDarkMode ? "Dark Mode" : "Light Mode" }}
      </strong>
    </p>

    <button @click="toggleTheme">
      {{ isDarkMode ? " Light Mode" : " Dark Mode" }}
    </button>
  </div>
</template>

<style>
.container {
  width: 500px;
  margin: 50px auto;
  padding: 40px;
  text-align: center;

  background-color: white;
  color: black;

  border: 1px solid #ccc;
  border-radius: 15px;

  transition: 0.3s;
}

/* Dark Mode */
.container.dark {
  background-color: #222;
  color: white;
  border-color: #555;
}

button {
  padding: 10px 20px;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  font-size: 16px;
}
</style> -->




///exercise 7
<!-- <script setup>
import { ref, computed } from 'vue'

// Array ផ្លែឈើ
const fruits = ref([
  "ផ្លែប៉ោម",
  "ចេក",
  "ក្រូច",
  "ស្វាយ",
  "ឪឡឹក",
  "មៀន",
  "សៅម៉ៅ",
  "ទុរេន"

])
// តម្លៃដែលអ្នកប្រើវាយក្នុង Input
const searchQuery = ref("")
// Filter ផ្លែឈើ
const filteredFruits = computed(() => {
  return fruits.value.filter((fruit) =>
    fruit.includes(searchQuery.value)
  )
})
</script>

<template>
  <div>
    <h1>🔎 ស្វែងរកផ្លែឈើ</h1>

    <!-- Search Input -->
    <!-- <input
      v-model="searchQuery"
      type="text"
      placeholder="វាយឈ្មោះផ្លែឈើ..."
    /> -->

    <!-- Result -->
    <!-- <ul> -->
      <!-- <li
        v-for="fruit in filteredFruits"
        :key="fruit"
      >
        {{ fruit }}
      </li>
    </ul>

    <!-- បង្ហាញពេលរកមិនឃើញ -->
    <!-- <p v-if="filteredFruits.length === 0">
      មិនមានលទ្ធផលទេ
    </p>
  </div> -->
<!-- </template>  -->

///exercise8
<!-- <script setup>
import { ref } from 'vue'

// Radio
const selectedLanguage = ref("")

// Checkbox
const agreed = ref(false)
</script>

<template>
  <div>
    <h1>ជ្រើសរើស Form</h1>

    <!-- Radio Buttons -->
    <!-- <h2>ជ្រើសរើសភាសាកូដដែលអ្នកចូលចិត្ត</h2>

    <label>
      <input
        type="radio"
        value="JavaScript"
        v-model="selectedLanguage"
      />
      JavaScript
    </label>

    <br />

    <label>
      <input
        type="radio"
        value="Python"
        v-model="selectedLanguage"
      />
      Python
    </label>

    <br />

    <label>
      <input
        type="radio"
        value="PHP"
        v-model="selectedLanguage"
      />
      PHP
    </label>

    <!-- Checkbox -->
    <!-- <h2>លក្ខខណ្ឌ</h2>

    <label>
      <input
        type="checkbox"
        v-model="agreed"
      />
      ខ្ញុំយល់ព្រមតាមលក្ខខណ្ឌ
    </label>

    <!-- Result -->
    <!-- <div class="result"> 
      <!-- <h2> លទ្ធផល</h2> --> 
      <!-- <p> -->
        <!-- <strong>ភាសាដែលបានជ្រើសរើស៖</strong> -->
        <!-- {{ selectedLanguage || "មិនទាន់ជ្រើសរើស" }} -->
      <!-- </p> -->
      <!-- <p> -->
        <!-- /<strong>ស្ថានភាពយល់ព្រម៖</strong> -->
        <!-- {{ agreed ? "បានយល់ព្រម" : "មិនទាន់យល់ព្រម" }} -->
      <!-- </p> -->
    <!-- </div> -->
  <!-- </div> -->
<!-- </template> -->


///exercise9
<!-- <script setup>
import { ref } from 'vue'

// Tab ដែលកំពុង Active
const activeTab = ref('Home')

// Function សម្រាប់ប្តូរ Tab
const changeTab = (tab) => {
  activeTab.value = tab
} -->
<!-- </script> -->

<!-- <template>
  <div class="container">

    <h1>📑 Tab Switcher</h1>

    <!-- Tabs -->
    <!-- <div class="tabs"> -->
      <!-- <button
        @click="changeTab('Home')"
        :class="{ active: activeTab === 'Home' }"
      >
        Home
      </button> -->

      <!-- <button
        @click="changeTab('About')"
        :class="{ active: activeTab === 'About' }"
      >
        About
      </button> -->

      <!-- <button
        @click="changeTab('Contact')"
        :class="{ active: activeTab === 'Contact' }"
      >
        Contact
      </button> -->
    <!-- </div> -->

    <!-- Home Content -->
    <!-- <div v-if="activeTab === 'Home'" class="content"> -->
      <!-- <h2>🏠 Home</h2>
      <p>
        សូមស្វាគមន៍មកកាន់ Home Page!
      </p>
      <p>
        នេះជាខ្លឹមសាររបស់ Home Tab។
      </p>
    </div> -->

    <!-- About Content -->
    <!-- <div v-else-if="activeTab === 'About'" class="content">
      <h2>👤 About</h2>
      <p>
        នេះជាទំព័រ About។
      </p>
      <p>
        នៅទីនេះយើងអាចដាក់ព័ត៌មានអំពី Website ឬ Project។
      </p>
    </div> -->

    <!-- Contact Content -->
    <!-- <div v-else-if="activeTab === 'Contact'" class="content">
      <h2>📞 Contact</h2>
      <p>
        អ្នកអាចទាក់ទងមកយើងតាមរយៈ Contact Page។
      </p>
      <p>
        Email: example@gmail.com
      </p>
    </div> -->

  <!-- </div>
</template> 







///exercise 10
<script setup>
// import { ref, computed } from 'vue'

// Textarea message
// const message = ref('')

const remainingChars = computed(() => {
  return 100 - message.value.length
})
</script>
<template>
  <div class="container">
    <h1>Character Counter</h1>
    <!-- Textarea -->
    <!-- <textarea
      v-model="message"
      maxlength="100"
      placeholder="វាយសាររបស់អ្នក..."
    ></textarea> -->
    <!-- <p
      :class="{ warning: remainingChars === 0 }"
    >
      អក្សរដែលនៅសល់៖ {{ remainingChars }}
    </p> -->
    <!-- <p
      v-if="remainingChars === 0"
      class="warning"
    >
      អ្នកបានវាយដល់ដែនកំណត់ហើយ!
    </p>
  </div>
</template> -->




///exersice 11

<!-- <script setup> -->
// import { ref, computed } from 'vue'

// const email = ref('')
// const password = ref('')

// // Email validation
// const emailValid = computed(() => {
//   return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email.value)
// })

// // Password validation
// const passwordLength = computed(() => {
//   return password.value.length >= 8
// })

// const hasUppercase = computed(() => {
//   return /[A-Z]/.test(password.value)
// })

// const hasNumber = computed(() => {
//   return /[0-9]/.test(password.value)
// })

// const hasSpecialChar = computed(() => {
//   return /[!@#$%^&*]/.test(password.value)
// })

// // Password strength
// const passwordStrength = computed(() => {
//   let score = 0

//   if (passwordLength.value) score++
//   if (hasUppercase.value) score++
//   if (hasNumber.value) score++
//   if (hasSpecialChar.value) score++

<!-- //   if (score <= 1) return 'ទន់ខ្សោយ' -->
<!-- //   if (score <= 3) return 'មធ្យម' -->

//   return 'ខ្លាំង'
// })

// IMPORTANT
// const formValid = computed(() => {
//   return (
//     emailValid.value &&
//     passwordLength.value &&
//     hasUppercase.value &&
//     hasNumber.value &&
//     hasSpecialChar.value
//   )
// })
// Submit
// function submitForm() {
//   alert('Submit បានជោគជ័យ! ')
// }
<!-- // </script> -->

<!-- // <template>
//   <div class="container">

//     <h1>Form Validation</h1>

//     <label>Email</label>

//     <input
//       v-model="email"
//       type="email"
//       placeholder="example@gmail.com"
//     />

//     <p v-if="email && emailValid" class="success">
//        Email ត្រឹមត្រូវ
//     </p>

//     <p v-if="email && !emailValid" class="error">
//        Email មិនត្រឹមត្រូវ
//     </p>

//     <label>Password</label>

//     <input
//       v-model="password"
//       type="password"
//       placeholder="Hello123!"
//     />
//     <p>
//       Password Strength:
//       <strong>{{ passwordStrength }}</strong>
//     </p>


//     <p :class="{ success: passwordLength, error: !passwordLength }">
//       {{ passwordLength ? '✓' : '✗' }}
//       យ៉ាងតិច ៨ តួអក្សរ
//     </p>

//     <p :class="{ success: hasUppercase, error: !hasUppercase }">
//       {{ hasUppercase ? '✓' : '✗' }}
//       មានអក្សរធំ (A-Z)
//     </p>

//     <p :class="{ success: hasNumber, error: !hasNumber }">
//       {{ hasNumber ? '✓' : '✗' }}
//       មានលេខ (0-9)
//     </p>

//     <p :class="{ success: hasSpecialChar, error: !hasSpecialChar }">
//       {{ hasSpecialChar ? '✓' : '✗' }}
//       មានសញ្ញាពិសេស (!@#$...)
//     </p>

//     <button
//       type="button"
//       :disabled="!formValid"
//       @click="submitForm"
//     >
//       Submit
//     </button>

//   </div>
// </template>
 -->


 ///exersice12

 <!-- <script setup>
import { ref, computed } from 'vue'

// 1. Array នៃផលិតផល
const products = ref([
  {
    name: 'iPhone 15',
    category: 'Electronics',
    price: 999,
    rating: 4.8
  },
  {
    name: 'Samsung Galaxy S24',
    category: 'Electronics',
    price: 899,
    rating: 4.7
  },
  {
    name: 'T-Shirt',
    category: 'Clothing',
    price: 25,
    rating: 4.2
  },
  {
    name: 'Jeans',
    category: 'Clothing',
    price: 50,
    rating: 4.5
  },
  {
    name: 'JavaScript Book',
    category: 'Books',
    price: 30,
    rating: 4.9
  },
  {
    name: 'Vue.js Book',
    category: 'Books',
    price: 35,
    rating: 4.6
  }
])

// 2. Search
const searchQuery = ref('')

// 3. Category
const selectedCategory = ref('ទាំងអស់')

// 4. Sort
const selectedSort = ref('')

// 5. computed តែមួយ
const filteredProducts = computed(() => {
  let result = products.value

  // Filter តាមឈ្មោះ
  if (searchQuery.value) {
    result = result.filter(product =>
      product.name
        .toLowerCase()
        .includes(searchQuery.value.toLowerCase())
    )
  }

  // Filter តាម Category
  if (selectedCategory.value !== 'ទាំងអស់') {
    result = result.filter(product =>
      product.category === selectedCategory.value
    )
  }

  // Sort
  if (selectedSort.value === 'price-asc') {
    result = [...result].sort((a, b) => a.price - b.price)
  }

  if (selectedSort.value === 'price-desc') {
    result = [...result].sort((a, b) => b.price - a.price)
  }

  if (selectedSort.value === 'rating-desc') {
    result = [...result].sort((a, b) => b.rating - a.rating)
  }

  return result
})
</script> -->

<!-- <template>
  <div class="container">
    <h1> Product Filter & Sort</h1>

    <!-- Controls -->
    <!-- <div > -->

      <!-- Search -->
      <!-- <input
        v-model="searchQuery"
        type="text"
        placeholder="ស្វែងរកផលិតផល..."
      /> -->

      <!-- Category -->
      <!-- <select v-model="selectedCategory">
        <option value="ទាំងអស់">ទាំងអស់</option>
        <option value="Electronics">Electronics</option>
        <option value="Clothing">Clothing</option>
        <option value="Books">Books</option>
      </select> -->

      <!-- Sort -->
      <!-- <select v-model="selectedSort">
        <option value=""> ជ្រើសរើស Sort</option>
        <option value="price-asc">
          តម្លៃពីទាបទៅខ្ពស់
        </option>
        <option value="price-desc">
          តម្លៃពីខ្ពស់ទៅទាប
        </option>
        <option value="rating-desc">
          Rating ខ្ពស់ជាងគេ
        </option>
      </select> -->

    <!-- </div> -->

    <!-- Products -->
    <!-- <div class="products">

      <div
        v-for="product in filteredProducts"
        :key="product.name"
        class="product"
      >
        <h2>{{ product.name }}</h2>

        <p>
          Category:
          <strong>{{ product.category }}</strong>
        </p>

        <p>
          Price:
          <strong>${{ product.price }}</strong>
        </p>

        <p>
           Rating:
          <strong>{{ product.rating }}</strong>
        </p>
      </div> -->

    <!-- </div>

    <!-- No result -->
    <!-- <p v-if="filteredProducts.length === 0">
       រកមិនឃើញផលិតផលទេ
    </p>

    <p> -->
      <!-- ចំនួនផលិតផល៖ {{ filteredProducts.length }}
    </p> -->
  <!-- </div> 
<!-- </template>  -->


///exersice 13
<!-- <script setup>
import { ref, watch, onMounted } from 'vue'

// Notes
const notes = ref([])

// Input
const title = ref('')
const content = ref('')
 -->

const addNote = () => {
  if (title.value.trim() === '' || content.value.trim() === '') {
    alert('សូមបំពេញ Title និង Content')
    return
  }
  notes.value.push({
    id: Date.now(),
    title: title.value,
    content: content.value
  })
  title.value = ''
  content.value = ''
}
const deleteNote = (id) => {
  notes.value = notes.value.filter(note => note.id !== id)
}
// =========================
// Watch
// Save notes → localStorage
// =========================
watch(
  notes,
  (newNotes) => {
    localStorage.setItem(
      'notes',
      JSON.stringify(newNotes)
    )
  },
  { deep: true }
)
// =========================
// onMounted
// Load notes from localStorage
// =========================
onMounted(() => {
  const savedNotes = localStorage.getItem('notes')
  if (savedNotes) {
    notes.value = JSON.parse(savedNotes)
  }
})
<!-- </script>

<template>
  <div >

    <h1>Simple Notes App</h1>

    
    <div>

      <input
        v-model="title"
        type="text"
        placeholder="Note Title"
      />
      <br>
      <br> -->

      <!-- <textarea
        v-model="content"
        placeholder="Note Content"
        rows="5"
      ></textarea>
      <br> -->
      <!-- <button @click="addNote">
         Add Note
      </button>
    </div> -->
    <!-- Notes -->
    <!-- <div class="notes">

      <div
        v-for="note in notes"
        :key="note.id"
        class="note"
      > -->

        <!-- <h2>{{ note.title }}</h2>

        <p>{{ note.content }}</p>

        <button
          class="delete"
          @click="deleteNote(note.id)"
        >
          Delete
        </button>

      </div> -->

    <!-- </div> -->

    <!-- Empty -->
    <!-- <p
      v-if="notes.length === 0"
      class="empty"
    >
      មិនទាន់មាន Note ទេ
    </p>

  </div> -->
<!-- </template> -->


///exersice 14

<!-- <script setup> -->
// import { ref, onMounted } from 'vue'

// =========================
// State
// =========================
// const data = ref([])
// const isLoading = ref(true)
// const errorMessage = ref(null)

// =========================
// Fetch Data
// =========================
const fetchUsers = async () => {
  try {
    isLoading.value = true
    errorMessage.value = null

    const response = await fetch(
      'https://jsonplaceholder.typicode.com/users'
    )

    // Check HTTP Error
    if (!response.ok) {
      throw new Error('មិនអាចទាញយកទិន្នន័យបានទេ')
    }

    // Convert JSON → JavaScript Array
    data.value = await response.json()

  } catch (error) {
    errorMessage.value = error.message
  } finally {
    isLoading.value = false
  }
}

// =========================
// Component Loaded
// =========================
onMounted(() => {
  fetchUsers()
})
<!-- </script> -->

<!-- <template>
  <div class="container">

    <h1>User List</h1>

    <!-- Loading -->
    <!-- <div -->
      v-if="isLoading"
      class="loading"
    >
       កំពុងទាញយកទិន្នន័យ...
    <!-- </div> -->

    <!-- Error -->
    <!-- <div
      v-else-if="errorMessage"
      class="error"
    >
      Error: {{ errorMessage }}
    </div> --> 

    <!-- Data -->
    <!-- <div
      v-else
      class="users"
    > -->

      <!-- <div
        v-for="user in data"
        :key="user.id"
        class="user"
      >
        <h2>{{ user.name }}</h2>

        <p>
           Email:
          <strong>{{ user.email }}</strong>
        </p>
      </div> -->

    <!-- </div>

  </div>
</template> -->

//exersice 15

<!-- <script setup>
import { ref, computed } from 'vue' -->

// =========================
// Cart Data
// =========================
const cart = ref([
  {
    id: 1,
    name: 'Laptop',
    price: 800,
    quantity: 1
  },
  {
    id: 2,
    name: 'Mouse',
    price: 25,
    quantity: 2
  },
  {
    id: 3,
    name: 'Keyboard',
    price: 50,
    quantity: 1
  }
])

// Promo Code
const promoCode = ref('')

// =========================
// Increase Quantity
// =========================
const increaseQuantity = (item) => {
  item.quantity++
}

// =========================
// Decrease Quantity
// =========================
const decreaseQuantity = (item) => {
  if (item.quantity > 1) {
    item.quantity--
  }
}

// =========================
// Remove Item
// =========================
const removeItem = (id) => {
  cart.value = cart.value.filter(item => item.id !== id)
}

// =========================
// 1. Subtotal
// =========================
const subtotal = computed(() => {
  return cart.value.reduce((total, item) => {
    return total + item.price * item.quantity
  }, 0)
})

// =========================
// 2. Discount Amount
// =========================
const discountAmount = computed(() => {
  if (promoCode.value.trim().toUpperCase() === 'DISCOUNT10') {
    return subtotal.value * 0.10
  }

  return 0
})

// =========================
// Price After Discount
// =========================
const afterDiscount = computed(() => {
  return subtotal.value - discountAmount.value
})

// =========================
// 3. VAT 10%
// =========================
const tax = computed(() => {
  return afterDiscount.value * 0.10
})

// =========================
// 4. Grand Total
// =========================
const grandTotal = computed(() => {
  return afterDiscount.value + tax.value
})
<!-- </script>

<template> -->
  <!-- <div class="container"> -->

    <!-- <h1>Shopping Cart</h1>

    <!-- Cart -->
    <!-- <div -->
      v-for="item in cart"
      :key="item.id"
      class="cart-item"
    > 

      <!-- <div>
        <h2>{{ item.name }}</h2>

        <p>
          Price:
          <strong>${{ item.price.toFixed(2) }}</strong>
        </p>
      </div> -->

      <!-- Quantity -->
      <!-- <div>

        <button @click="decreaseQuantity(item)">
          quantity
        </button>

        <span>{{ item.quantity }}</span>

        <button @click="increaseQuantity(item)">
          increase
        </button>

      </div> -->

      <!-- Item Total -->
      <!-- <p class="item-total">
        ${{ (item.price * item.quantity).toFixed(2) }}
      </p> -->

      <!-- Delete -->
      <!-- <button
        class="delete"
        @click="removeItem(item.id)"
      >
        delete
      </button> -->

    <!-- </div> -->

    <!-- Empty Cart -->
    <!-- <div
      v-if="cart.length === 0"
      class="empty"
    >
       Cart is empty
    </div> -->

    <!-- Promo Code -->
    <!-- <div class="promo"> -->

      <!-- <label>Promo Code</label>

      <input -->
        v-model="promoCode"
        type="text"
        placeholder="ឧ. DISCOUNT10"
      />

      <!-- <p
        v-if="promoCode.toUpperCase() === 'DISCOUNT10'"
        class="success"
      >
         Discount 10% បានអនុវត្ត!
      </p> -->

    <!-- </div> -->

    <!-- Summary -->
    <!-- <div class="summary">

      <div>
        <span>Subtotal:</span>
        <strong>${{ subtotal.toFixed(2) }}</strong>
      </div> -->

      <!-- <div>
        <span>Discount:</span>
        <strong class="discount">
          - ${{ discountAmount.toFixed(2) }}
        </strong>
      </div> -->

      <!-- <div>
        <span>After Discount:</span>
        <strong>${{ afterDiscount.toFixed(2) }}</strong>
      </div> -->

      <!-- <div>
        <span>VAT (10%):</span>
        <strong>${{ tax.toFixed(2) }}</strong>
      </div> -->

      <!-- <hr />

      <div class="grand-total">
        <span>Grand Total:</span>
        <strong>${{ grandTotal.toFixed(2) }}</strong>
      </div> -->

    <!-- </div>

  </div>
</template> -->





<!-- <script setup> -->
 //import { ref, computed } from 'vue' 
//  import TodoItem from './TodoItem.vue' 


// const tasks = ref([
//   { id: 1, title: 'Personal Work No. 1', completed: true, category: 'Personal' },
//   { id: 2, title: 'Personal Work No. 2', completed: false, category: 'Personal' },
//   { id: 3, title: 'Personal Work No. 3', completed: false, category: 'Personal' },
//   { id: 4, title: 'Personal Work No. 4', completed: true, category: 'Personal' },
//   { id: 5, title: 'Personal Work No. 5', completed: false, category: 'Personal' }
// ])

// const newTask = ref('')
// const activeTab = ref('Personal')

// const addTask = () => {
//   if (newTask.value.trim() !== '') {
//     tasks.value.push({
//       id: Date.now(),
//       title: newTask.value,
//       completed: false,
//       category: activeTab.value
//     })
//     newTask.value = ''
//   }
// }

// const toggleTask = (id) => {
//   const task = tasks.value.find(t => t.id === id)
//   if (task) {
//     task.completed = !task.completed
//   }
// }

// const deleteTask = (id) => {
//   tasks.value = tasks.value.filter(task => task.id !== id)
// }

// const clearCompleted = () => {
//   tasks.value = tasks.value.filter(task => !task.completed)
// }

// const filteredTasks = computed(() => {
//   return tasks.value.filter(task => task.category === activeTab.value)
// })
<!-- //  </script>  -->
<!-- {/* <template> */} -->
  <!-- // <div class="app-container"> -->
  <!-- //   <div class="task-box"> -->
      
  //     <!-- Tabs ក្បាលលើ -->
  <!-- //     <div class="tabs"> -->
        <!-- // <button -->
          class="tab"
          :class="{ active: activeTab === 'Personal' }"
          @click="activeTab = 'Personal'"
        >
          Personal
        <!-- </button> -->
        <!-- <button -->
          class="tab"
          :class="{ active: activeTab === 'Professional' }"
          @click="activeTab = 'Professional'"
        >
          Professional
        <!-- </button> -->
      <!-- </div> -->

      <!-- ប្រអប់បញ្ចូល Add Task -->
      <!-- <div class="add-section"> -->
        <!-- <input -->
          v-model="newTask"
          @keyup.enter="addTask"
          type="text"
          placeholder="What do you need to do?"
        />
        <!-- <button class="add-btn" @click="addTask">ADD</button> -->
      <!-- </div> -->

      
      <!-- <div class="task-card-body"> -->
        <!-- <div class="task-list"> -->
          <!-- <TodoItem -->
            v-for="task in filteredTasks"
            :key="task.id"
            :title="task.title"
            :completed="task.completed"
            @toggle="toggleTask(task.id)"
            @delete="deleteTask(task.id)"
          />
          <!-- <div v-if="filteredTasks.length === 0" class="empty"> -->
            No tasks in {{ activeTab }} yet
          <!-- </div> -->
        <!-- </div> -->

        
        <!-- <div class="action-footer"> -->
          <!-- <button class="clear-btn" @click="clearCompleted"> -->
            <!-- <span class="clear-icon">✕</span> Clear Completed -->
          <!-- </button> -->
        <!-- </div> -->
      <!-- </div> -->

    <!-- </div> -->
  <!-- </div> -->
<!-- </template> -->

<!-- <style scoped> -->

.app-container {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 80vh;
  padding: 20px;
}

.task-box {
  width: 100%;
  max-width: 550px;
  background: #ffffff;
  border-radius: 8px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
  overflow: hidden;
  font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
}

/* របារ Tabs ខាងលើ */
.tabs {
  display: flex;
  border-bottom: 2px solid #f0f0f0;
}

.tab {
  flex: 1;
  padding: 15px;
  border: none;
  background: #fdfdfd;
  font-size: 16px;
  font-weight: bold;
  color: #b3b3b3;
  cursor: pointer;
  position: relative;
  transition: color 0.2s;
}

.tab.active {
  color: #4a3f35;
}

/* បន្ទាត់ពណ៌លឿងទុំខាងក្រោម Tab ដែល Active */
.tab.active::after {
  content: '';
  position: absolute;
  bottom: -2px;
  left: 0;
  width: 100%;
  height: 3px;
  background-color: #df8c25;
}

/* ផ្នែក Add Section */
.add-section {
  display: flex;
  padding: 20px 25px 15px 25px;
  gap: 0;
}

.add-section input {
  flex: 1;
  padding: 12px 20px;
  border: 1px solid #ebdcd0;
  border-right: none;
  border-top-left-radius: 20px;
  border-bottom-left-radius: 20px;
  background-color: #f7f1eb;
  font-size: 15px;
  outline: none;
  color: #61554a;
}

.add-section input::placeholder {
  color: #bdae9f;
}

.add-btn {
  padding: 0 25px;
  background-color: #72b2c4;
  color: white;
  border: none;
  border-top-right-radius: 20px;
  border-bottom-right-radius: 20px;
  font-size: 15px;
  font-weight: bold;
  cursor: pointer;
  transition: background-color 0.2s;
}

.add-btn:hover {
  background-color: #5c9cae;
}

.task-card-body {
  background-color:rgb(20, 101, 117);
  margin: 10px 25px 25px 25px;
  border-radius: 16px;
  padding: 15px 20px 10px 20px;
}

.task-list {
  min-height: 100px;
}

.empty {
  text-align: center;
  color: #a89a8c;
  padding: 30px 0;
  font-size: 14px;
}

/* ផ្នែក Footer ប៊ូតុងលុប */
.action-footer {
  display: flex;
  justify-content: flex-end;
  margin-top: 15px;
  padding-top: 5px;
}

.clear-btn {
  background: transparent;
  border: none;
  color: #df8c25;
  font-size: 13px;
  font-weight: 500;
  cursor: pointer;
  display: flex;
  align-items: center;
  gap: 4px;
}

.clear-icon {
  font-size: 10px;
  border: 1px solid #df8c25;
  border-radius: 3px;
  padding: 0 3px;
  display: inline-block;
}

.clear-btn:hover {
  text-decoration: underline;
}
<!-- </style> -->



///Info 


<!-- <script setup>
// import { ref } from 'vue'

// const darkMode = ref(false)

const projects = [
  {
    title: 'Lamborghini Website',
    description: 'A modern responsive website built with HTML, CSS and JavaScript.',
    tech: 'HTML • CSS • JavaScript'
  },
  {
    title: 'Todo App',
    description: 'A simple Todo application built with Vue 3.',
    tech: 'Vue 3 • Vite'
  },
  {
    title: 'Shopping Cart',
    description: 'Product filtering, sorting and cart management application.',
    tech: 'Vue 3 • JavaScript'
  }
]

const skills = [
  'HTML',
  'CSS',
  'JavaScript',
  'Vue.js',
  'React',
  'Tailwind CSS',
  'Git & GitHub'
]
</script>

<!-- <template> -->
  <!-- <div :class="{ dark: darkMode }" class="portfolio"> -->

    <!-- Navbar -->
    <!-- <header class="navbar"> -->
      <!-- <div class="container nav-content"> -->
        <!-- <h2 class="logo">HEAB<span>.</span></h2> -->

        <!-- <nav>
          <a href="#home">Home</a>
          <a href="#about">About</a>
          <a href="#skills">Skills</a>
          <a href="#projects">Projects</a>
          <a href="#contact">Contact</a>
        </nav> -->

        <!-- <button class="theme-btn" @click="darkMode = !darkMode">
          {{ darkMode ? '☀️' : '🌙' }}
        </button> -->
     <!-- </div> -->
    <!-- </header> -->

    <!-- Hero -->
    <!-- <section id="home" class="hero"> -->
      <!-- <div class="container hero-content"> -->

        <!-- <div class="hero-text"> -->
          <!-- <p class="hello">Hello, I'm</p> -->

          <!-- <h1> -->
            <!-- HEAB <span>YEN</span> -->
          <!-- </h1> -->

          <!-- <h2>Frontend Developer</h2> -->

          <!-- <p class="description"> -->
            I create modern, responsive and user-friendly
            web applications using modern web technologies.
          <!-- </p> -->

          <!-- <div class="buttons"> -->
            <!-- <a href="#projects" class="btn primary"> -->
              View Projects
            <!-- </a> -->

            <!-- <a href="#contact" class="btn secondary"> -->
              Contact Me
            <!-- </a> -->
          <!-- </div>  -->
        <!-- </div> -->

        <!-- <div class="hero-card"> -->
          <!-- <div class="profile-circle"> -->
            HY
          <!-- </div> -->
        <!-- </div> -->

      <!-- </div> -->
    <!-- </section> -->

    <!-- About -->
    <!-- <section id="about" class="section"> -->
      <!-- <div class="container"> -->

        <!-- <p class="section-subtitle">WHO I AM</p>
        <h2 class="section-title">About Me</h2>

        <div class="about-content"> -->
          <!-- <div>
            <h3>I'm a Frontend Developer</h3>

            <p>
              My name is <strong>Heab Yen</strong>. I am passionate
              about creating websites and web applications.
            </p>

            <p>
              I enjoy learning new technologies and improving my
              programming skills by building real projects.
            </p>
          </div> -->

          <!-- <div class="about-box">
            <div>
              <strong>3+</strong>
              <span>Projects</span>
            </div> -->

            <!-- <div>
              <strong>7+</strong>
              <span>Skills</span>
            </div> -->

            <!-- <div>
              <strong>1+</strong>
              <span>Years Learning</span>
            </div> -->
          <!-- </div>
        </div>

      </div> -->
    <!-- </section> -->

    <!-- Skills -->
    <!-- <section id="skills" class="section skills-section"> -->
      <!-- <div class="container">

        <p class="section-subtitle">WHAT I KNOW</p>
        <h2 class="section-title">My Skills</h2>

        <div class="skills-grid">
          <div
            v-for="skill in skills"
            :key="skill"
            class="skill-card"
          >
            <h3>{{ skill }}</h3>
            <div class="skill-line"></div>
          </div> -->
        <!-- </div>

      </div>
    </section>

    <!-- Projects -->
    <!-- <section id="projects" class="section"> -->
      <!-- <div class="container">

        <p class="section-subtitle">MY WORK</p>
        <h2 class="section-title">Projects</h2>

        <div class="projects-grid">

          <div -->
            v-for="project in projects"
            :key="project.title"
            class="project-card"
          >
            <!-- <div class="project-image"> -->
              {{ project.title.charAt(0) }}
            <!-- </div> --> 

            <!-- <div class="project-content"> -->
              <!-- <h3>{{ project.title }}</h3> -->

              <!-- <p>
                {{ project.description }}
              </p> -->

              <!-- <small>
                {{ project.tech }}
              </small> -->

              <!-- <button class="project-btn">
                View Project →
              </button> -->
            <!-- </div> -->
          <!-- </div> -->

        <!-- </div> -->

      <!-- </div> -->
    <!-- </section> -->

    <!-- Contact -->
    <!-- <section id="contact" class="section contact-section"> -->
      <!-- <div class="container"> -->

        <!-- <p class="section-subtitle">GET IN TOUCH</p>
        <h2 class="section-title">Contact Me</h2>

        <div class="contact-content"> -->

          <!-- <div class="contact-info"> -->
            <!-- <h3>Let's work together</h3> -->

            <!-- <p>
              If you have a project or want to contact me,
              feel free to send me a message.
            </p> -->

            <!-- <p>📧 Email: your-email@gmail.com</p>
            <p>📱 Phone: +855 XX XXX XXX</p>
            <p>📍 Cambodia</p>
          </div> -->

          <!-- <form class="contact-form" @submit.prevent>
            <input
              type="text"
              placeholder="Your Name"
            /> -->

            <!-- <input
              type="email"
              placeholder="Your Email"
            /> -->

            <!-- <textarea
              rows="5"
              placeholder="Your Message"
            ></textarea> -->

            <!-- <button type="submit" class="btn primary">
              Send Message
            </button>
          </form> -->

        <!-- </div>

      </div>
    /section>

    <!-- Footer -->
    <!-- <footer> -->
      <!-- <p> -->
        <!-- © 2026 <strong>HEAB YEN</strong>. All rights reserved. -->
      <!-- </p> -->
    <!-- </footer> -->

  <!-- </div> -->
<!-- </template> -->

<!-- <style scope> -->
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  scroll-behavior: smooth;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

.portfolio {
  min-height: 100vh;
  background: #ffffff;
  color: #222;
  transition: 0.3s;
}

.portfolio.dark {
  background: #111827;
  color: #ffffff;
}

/* Container */

.container {
  width: 90%;
  max-width: 1100px;
  margin: auto;
}

/* Navbar */

.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 100;
  background: rgba(255, 255, 255, 0.95);
  border-bottom: 1px solid #eee;
}

.dark .navbar {
  background: rgba(17, 24, 39, 0.95);
  border-color: #374151;
}

.nav-content {
  height: 70px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo {
  font-size: 25px;
}

.logo span {
  color: #6366f1;
}

nav {
  display: flex;
  gap: 30px;
}

nav a {
  text-decoration: none;
  color: inherit;
  font-weight: 500;
}

nav a:hover {
  color: #6366f1;
}

.theme-btn {
  border: none;
  background: transparent;
  font-size: 20px;
  cursor: pointer;
}

/* Hero */

.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  padding-top: 70px;
}

.hero-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 60px;
}

.hero-text {
  max-width: 650px;
}

.hello {
  color: #6366f1;
  font-size: 20px;
  margin-bottom: 10px;
}

.hero h1 {
  font-size: 65px;
  margin-bottom: 10px;
}

.hero h1 span {
  color: #6366f1;
}

.hero h2 {
  font-size: 30px;
  margin-bottom: 20px;
}

.description {
  color: #666;
  line-height: 1.8;
  font-size: 17px;
  max-width: 600px;
}

.dark .description {
  color: #d1d5db;
}

/* Buttons */

.buttons {
  display: flex;
  gap: 15px;
  margin-top: 30px;
}

.btn {
  display: inline-block;
  padding: 13px 25px;
  border-radius: 8px;
  text-decoration: none;
  border: none;
  cursor: pointer;
  font-size: 15px;
}

.primary {
  background: #6366f1;
  color: white;
}

.primary:hover {
  background: #4f46e5;
}

.secondary {
  border: 1px solid #6366f1;
  color: #6366f1;
}

/* Profile */

.hero-card {
  width: 300px;
  height: 300px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.profile-circle {
  width: 250px;
  height: 250px;
  border-radius: 50%;
  background: #6366f1;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
  font-size: 65px;
  font-weight: bold;
  box-shadow: 0 20px 50px rgba(99, 102, 241, 0.3);
}

/* Sections */

.section {
  padding: 100px 0;
}

.section-subtitle {
  color: #6366f1;
  font-weight: bold;
  text-align: center;
  margin-bottom: 10px;
}

.section-title {
  text-align: center;
  font-size: 40px;
  margin-bottom: 50px;
}

/* About */

.about-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  align-items: center;
}

.about-content h3 {
  font-size: 28px;
  margin-bottom: 20px;
}

.about-content p {
  color: #666;
  line-height: 1.8;
  margin-bottom: 15px;
}

.dark .about-content p {
  color: #d1d5db;
}

.about-box {
  display: flex;
  gap: 15px;
}

.about-box div {
  flex: 1;
  padding: 25px 10px;
  text-align: center;
  border-radius: 10px;
  background: #f3f4f6;
}

.dark .about-box div {
  background: #1f2937;
}

.about-box strong {
  display: block;
  font-size: 30px;
  color: #6366f1;
}

.about-box span {
  font-size: 13px;
}

/* Skills */

.skills-section {
  background: #f8f9ff;
}

.dark .skills-section {
  background: #0f172a;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 20px;
}

.skill-card {
  padding: 30px 20px;
  background: white;
  border-radius: 10px;
  text-align: center;
  box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);
}

.dark .skill-card {
  background: #1f2937;
}

.skill-card h3 {
  margin-bottom: 15px;
}

.skill-line {
  height: 4px;
  width: 50px;
  background: #6366f1;
  margin: auto;
}

/* Projects */

.projects-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 25px;
}

.project-card {
  overflow: hidden;
  border-radius: 12px;
  background: white;
  box-shadow: 0 5px 25px rgba(0, 0, 0, 0.08);
}

.dark .project-card {
  background: #1f2937;
}

.project-image {
  height: 180px;
  background: #6366f1;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-size: 60px;
  font-weight: bold;
}

.project-content {
  padding: 25px;
}

.project-content h3 {
  margin-bottom: 15px;
}

.project-content p {
  color: #666;
  line-height: 1.6;
  margin-bottom: 15px;
}

.dark .project-content p {
  color: #d1d5db;
}

.project-content small {
  color: #6366f1;
}

.project-btn {
  display: block;
  margin-top: 20px;
  padding: 10px 15px;
  border: none;
  background: transparent;
  color: #6366f1;
  cursor: pointer;
}

/* Contact */

.contact-section {
  background: #f8f9ff;
}

.dark .contact-section {
  background: #0f172a;
}

.contact-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
}

.contact-info h3 {
  font-size: 28px;
  margin-bottom: 20px;
}

.contact-info p {
  line-height: 1.8;
  margin-bottom: 15px;
  color: #666;
}

.dark .contact-info p {
  color: #d1d5db;
}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.contact-form input,
.contact-form textarea {
  width: 100%;
  padding: 15px;
  border: 1px solid #ddd;
  border-radius: 8px;
  font-size: 15px;
  font-family: inherit;
}

.dark .contact-form input,
.dark .contact-form textarea {
  background: #1f2937;
  color: white;
  border-color: #374151;
}

/* Footer */

footer {
  text-align: center;
  padding: 30px;
  border-top: 1px solid #eee;
}

.dark footer {
  border-color: #374151;
}

/* Responsive */

@media (max-width: 768px) {

  nav {
    display: none;
  }

  .hero-content {
    flex-direction: column;
    text-align: center;
  }

  .hero h1 {
    font-size: 45px;
  }

  .hero h2 {
    font-size: 24px;
  }

  .buttons {
    justify-content: center;
  }

  .hero-card {
    width: 220px;
    height: 220px;
  }

  .profile-circle {
    width: 190px;
    height: 190px;
    font-size: 50px;
  }

  .about-content,
  .contact-content {
    grid-template-columns: 1fr;
  }

  .skills-grid {
    grid-template-columns: repeat(2, 1fr);
  }

  .projects-grid {
    grid-template-columns: 1fr;
  }

  .about-box {
    flex-direction: column;
  }
}
<!-- </style> -->
 



//Mini E-Commerce
<!-- <script setup>
import { ref, computed, watch, onMounted } from 'vue'

const products = ref([
  {
    id: 1,
    name: 'iPhone 15',
    category: 'Electronics',
    price: 999,
    stock: 10
  },
  {
    id: 2,
    name: 'Laptop HP',
    category: 'Electronics',
    price: 750,
    stock: 5
  },
  {
    id: 3,
    name: 'Pizza',
    category: 'Food',
    price: 8,
    stock: 20
  },
  {
    id: 4,
    name: 'Burger',
    category: 'Food',
    price: 5,
    stock: 15
  },
  {
    id: 5,
    name: 'T-Shirt',
    category: 'Fashion',
    price: 15,
    stock: 30
  }
])

const cart = ref([])

const searchQuery = ref('')
const selectedCategory = ref('All')
const sortBy = ref('default')

const promoCode = ref('')

const newProduct = ref({
  name: '',
  category: 'Electronics',
  price: '',
  stock: ''
})

const filteredProducts = computed(() => {
  let result = products.value.filter(product => {
    const search = product.name
      .toLowerCase()
      .includes(searchQuery.value.toLowerCase())

    const category =
      selectedCategory.value === 'All' ||
      product.category === selectedCategory.value

    return search && category
  })

  if (sortBy.value === 'low-high') {
    result.sort((a, b) => a.price - b.price)
  }

  if (sortBy.value === 'high-low') {
    result.sort((a, b) => b.price - a.price)
  }

  return result
})

function addProduct() {
  if (!newProduct.value.name.trim()) {
    alert('Please enter product name')
    return
  }

  if (newProduct.value.price <= 0) {
    alert('Price must be greater than 0')
    return
  }

  if (newProduct.value.stock < 0 || newProduct.value.stock === '') {
    alert('Stock cannot be negative')
    return
  }

  products.value.push({
    id: Date.now(),
    name: newProduct.value.name,
    category: newProduct.value.category,
    price: Number(newProduct.value.price),
    stock: Number(newProduct.value.stock)
  })

  newProduct.value = {
    name: '',
    category: 'Electronics',
    price: '',
    stock: ''
  }
}

function deleteProduct(id) {
  const inCart = cart.value.find(item => item.id === id)

  if (inCart) {
    alert('Cannot delete product in cart')
    return
  }

  products.value = products.value.filter(
    product => product.id !== id
  )
}

function addToCart(product) {
  if (product.stock <= 0) {
    alert('Out of stock!')
    return
  }

  const item = cart.value.find(
    item => item.id === product.id
  )

  if (item) {
    item.quantity++
  } else {
    cart.value.push({
      id: product.id,
      name: product.name,
      price: product.price,
      quantity: 1
    })
  }

  product.stock--
}

function increaseQuantity(item) {
  const product = products.value.find(
    product => product.id === item.id
  )

  if (!product) return

  if (product.stock <= 0) {
    alert('No more stock!')
    return
  }

  item.quantity++
  product.stock--
}

function decreaseQuantity(item) {
  const product = products.value.find(
    product => product.id === item.id
  )

  if (item.quantity > 1) {
    item.quantity--

    if (product) {
      product.stock++
    }
  } else {
    removeFromCart(item.id)
  }
}

function removeFromCart(id) {
  const item = cart.value.find(
    item => item.id === id
  )

  if (!item) return

  const product = products.value.find(
    product => product.id === id
  )

  if (product) {
    product.stock += item.quantity
  }

  cart.value = cart.value.filter(
    item => item.id !== id
  )
}

const subtotal = computed(() => {
  return cart.value.reduce(
    (total, item) => total + item.price * item.quantity,
    0
  )
})

const discountRate = computed(() => {
  return promoCode.value.toUpperCase() === 'SAVE20'
    ? 0.2
    : 0
})

const discount = computed(() => {
  return subtotal.value * discountRate.value
})

const grandTotal = computed(() => {
  return subtotal.value - discount.value
})

const cartCount = computed(() => {
  return cart.value.reduce(
    (total, item) => total + item.quantity,
    0
  )
})

watch(
  products,
  value => {
    localStorage.setItem(
      'products',
      JSON.stringify(value)
    )
  },
  { deep: true }
)

watch(
  cart,
  value => {
    localStorage.setItem(
      'cart',
      JSON.stringify(value)
    )
  },
  { deep: true }
)

onMounted(() => {
  const savedProducts = localStorage.getItem('products')
  const savedCart = localStorage.getItem('cart')

  if (savedProducts) {
    products.value = JSON.parse(savedProducts)
  }

  if (savedCart) {
    cart.value = JSON.parse(savedCart)
  }
})
</script> -->

<!-- <template> -->
  <!-- <div class="app"> -->

    <!-- <header class="header">
      <h1> My Store</h1>

      <div class="cart-count">
        Cart: {{ cartCount }}
      </div>
    </header> -->

    <!-- PRODUCTS -->
    <!-- <section class="section">
      <h2>Product Catalog</h2>

      <div class="filters">
        <input
          v-model="searchQuery"
          type="text"
          placeholder="Search product..."
        />

        <select v-model="selectedCategory">
          <option value="All">All Categories</option>
          <option value="Electronics">Electronics</option>
          <option value="Food">Food</option>
          <option value="Fashion">Fashion</option>
        </select>

        <select v-model="sortBy">
          <option value="default">តម្រៀប</option>
          <option value="low-high">Price: Low → High</option>
          <option value="high-low">Price: High → Low</option>
        </select> -->
      <!-- </div>

      <div class="product-grid">
        <div
          v-for="product in filteredProducts"
          :key="product.id"
          class="product-card"
        >
          <h3>{{ product.name }}</h3>

          <p class="category">
            {{ product.category }}
          </p>

          <p class="price">
            ${{ product.price.toFixed(2) }}
          </p>

          <p>
            Stock:
            <strong
              :class="{ out: product.stock === 0 }"
            >
              {{ product.stock }}
            </strong>
          </p>

          <div class="button-group">
            <button
              class="buy-btn"
              @click="addToCart(product)"
              :disabled="product.stock === 0"
            >
              {{ product.stock === 0 ? 'Out of Stock' : 'Buy' }}
            </button>

            <button
              class="delete-btn"
              @click="deleteProduct(product.id)"
            >
              Delete
            </button>
          </div> -->
        <!-- </div> -->
      <!-- </div> -->

      <!-- <p
        v-if="filteredProducts.length === 0"
        class="empty"
      >
        No products found.
      </p> -->
    <!-- </section>

    
    <section class="section">
      <h2> Add Product</h2>

      <form
        class="product-form"
        @submit.prevent="addProduct"
      >
        <input
          v-model="newProduct.name"
          type="text"
          placeholder="Product name"
        />

        <select v-model="newProduct.category">
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
          v-model.number="newProduct.price"
          type="number"
          min="0"
          placeholder="តម្លៃ$"
        />

        <input
          v-model.number="newProduct.stock"
          type="number"
          min="0"
          placeholder="Stock"
        />
        <br>
        <br>
        <button type="submit">
          Add Product
        </button>
      </form>
    </section> -->

    <!-- CART -->
    <!-- <section class="section">
      <h2> Shopping Cart</h2>

      <div
        v-if="cart.length === 0"
        class="empty"
      >
        Your cart is empty.
      </div>

      <div
        v-for="item in cart"
        :key="item.id"
        class="cart-item"
      >
        <div>
          <h3>{{ item.name }}</h3>
          <p>${{ item.price.toFixed(2) }}</p>
        </div>

        <div class="quantity">
          <button @click="decreaseQuantity(item)">
            
          </button>

          <span>{{ item.quantity }}</span>

          <button @click="increaseQuantity(item)">
            
          </button>
        </div>

        <strong>
          ${{ (item.price * item.quantity).toFixed(2) }}
        </strong>

        <button
          class="remove-btn"
          @click="removeFromCart(item.id)"
        >
          Remove
        </button>
      </div>
    </section> -->

    
    <!-- <section class="section checkout">
      <h2> Checkout Summary</h2>

      <input
        v-model="promoCode"
        type="text"
        placeholder="Promo Code: SAVE20"
      />

      <p
        v-if="promoCode && discountRate > 0"
        class="success"
      >
        ✓ 20% Discount Applied
      </p>

      <p
        v-else-if="promoCode"
        class="error"
      >
        Invalid promo code
      </p>

      <div class="summary">
        <div>
          <span>ទឹកប្រាក់ត្រូវបង់:</span>
          <strong>
            ${{ subtotal.toFixed(2) }}
          </strong>
        </div>

        <!-- <div>
          <span>បញ្ជុះតម្លៃ:</span>
          <strong class="discount">
            -${{ discount.toFixed(2) }}
          </strong>
        </div> -->

        <hr />

        <!-- <div class="total">
          <span>Grand Total</span>
          <strong>
            ${{ grandTotal.toFixed(2) }}
          </strong>
        </div> -->
      <!-- </div> -->

      <!-- <button
        class="checkout-btn"
        :disabled="cart.length === 0"
      >
        Checkout
      </button> -->
    <!-- </section> --> 

  <!-- </div> -->
<!-- </template> -->

<!-- <style scoped> -->
* {
  box-sizing: border-box;
} 

 .app { 
  max-width: 1200px;
  margin: auto;
  padding: 30px;
  font-family: Arial, sans-serif;
  background: #caccd4;
  min-height: 100vh;
 }  

 .header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 25px;
} 

 .header h1 {
  margin: 0;
} 

 .cart-count {
  background: #222;
  color: white;
  padding: 10px 18px;
  border-radius: 20px;
} 

 .section {
  background: white;
  padding: 25px;
  border-radius: 15px;
  margin-bottom: 25px;
  box-shadow: 0 3px 15px rgba(0, 0, 0, 0.08);
} 

 .filters {
  display: flex;
  gap: 10px;
  margin-bottom: 25px;
} 
 input,
select {
  padding: 11px;
  border: 1px solid #ddd;
  border-radius: 8px;
  font-size: 15px;
}

.filters input {
  flex: 1;
} 

.product-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

 .product-card {
  border: 1px solid #eee;
  padding: 20px;
  border-radius: 12px;
}

.product-card h3 {
  margin-top: 0;
}

.category {
  color: #777;
}

.price {
  font-size: 22px;
  font-weight: bold;
}

.out {
  color: red;
}

.button-group {
  display: flex;
  gap: 8px;
  margin-top: 15px;
}

button {
  border: none;
  padding: 10px 15px;
  border-radius: 8px;
  cursor: pointer;
  font-weight: bold;
  
}

button:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}

.buy-btn {
  background: #222;
  color: white;
  flex: 1;
}

.delete-btn,
.remove-btn {
  background: #ffe0e0;
  color: #d00;
}

.product-form {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr 1fr auto;
  gap: 10px;
}

.product-form button {
  background: #222;
  color: white;
}

.cart-item {
  display: grid;
  grid-template-columns: 1fr auto auto auto;
  align-items: center;
  gap: 20px;
  padding: 15px 0;
  border-bottom: 1px solid #eee;
}

.cart-item h3 {
  margin: 0;
}

.quantity {
  display: flex;
  align-items: center;
  gap: 10px;
}

.quantity button {
  width: 35px;
  height: 35px;
  padding: 0;
  background: #eee;
  font-size: 20px;
}

.checkout > input {
  width: 100%;
}

.summary {
  max-width: 450px;
  margin: 20px 0 0 auto;
}

.summary > div {
  display: flex;
  justify-content: space-between;
  padding: 10px 0;
}

.discount {
  color: green;
}

.total {
  font-size: 22px;
}

.checkout-btn {
  width: 100%;
  margin-top: 20px;
  background: #222;
  color: white;
  font-size: 17px;
}

.success {
  color: green;
}

.error {
  color: red;
}

.empty {
  text-align: center;
  padding: 30px;
  color: #777;
}

@media (max-width: 768px) {
  .app {
    padding: 15px;
  }

  .header {
    flex-direction: column;
    gap: 15px;
  }

  .filters {
    flex-direction: column;
  }

  .product-grid {
    grid-template-columns: 1fr;
  }

  .product-form {
    grid-template-columns: 1fr;
  }

  .cart-item {
    grid-template-columns: 1fr;
    gap: 10px;
  }
  
}
<!-- </style>  -->





<script setup>
import { ref, computed, watch, onMounted } from 'vue'

import Header from './components/Header.vue'
import ProductCatalog from './components/ProductCatalog.vue'
import AddProduct from './components/AddProduct.vue'
import ShoppingCart from './components/ShoppingCart.vue'
import CheckoutSummary from './components/CheckoutSummary.vue'
import ProductCart from './components/ProductCart.vue'

const products = ref([
  {
    id: 1,
    name: 'iPhone 15',
    category: 'Electronics',
    price: 999,
    stock: 10
  },
  {
    id: 2,
    name: 'Laptop HP',
    category: 'Electronics',
    price: 750,
    stock: 5
  },
  {
    id: 3,
    name: 'Pizza',
    category: 'Food',
    price: 8,
    stock: 20
  },
  {
    id: 4,
    name: 'Burger',
    category: 'Food',
    price: 5,
    stock: 15
  },
  {
    id: 5,
    name: 'T-Shirt',
    category: 'Fashion',
    price: 15,
    stock: 30
  }
])

const cart = ref([])

const searchQuery = ref('')
const selectedCategory = ref('All')
const sortBy = ref('default')

const promoCode = ref('')

const newProduct = ref({
  name: '',
  category: 'Electronics',
  price: '',
  stock: ''
})

const filteredProducts = computed(() => {
  let result = products.value.filter(product => {
    const search = product.name
      .toLowerCase()
      .includes(searchQuery.value.toLowerCase())

    const category =
      selectedCategory.value === 'All' ||
      product.category === selectedCategory.value

    return search && category
  })

  if (sortBy.value === 'low-high') {
    result.sort((a, b) => a.price - b.price)
  }

  if (sortBy.value === 'high-low') {
    result.sort((a, b) => b.price - a.price)
  }

  return result
})

function addProduct() {
  if (!newProduct.value.name.trim()) {
    alert('Please enter product name')
    return
  }

  if (newProduct.value.price <= 0) {
    alert('Price must be greater than 0')
    return
  }

  if (
    newProduct.value.stock < 0 ||
    newProduct.value.stock === ''
  ) {
    alert('Stock cannot be negative')
    return
  }

  products.value.push({
    id: Date.now(),
    name: newProduct.value.name,
    category: newProduct.value.category,
    price: Number(newProduct.value.price),
    stock: Number(newProduct.value.stock)
  })

  newProduct.value = {
    name: '',
    category: 'Electronics',
    price: '',
    stock: ''
  }
}

function deleteProduct(id) {
  const inCart = cart.value.find(item => item.id === id)

  if (inCart) {
    alert('Cannot delete product in cart')
    return
  }

  products.value = products.value.filter(
    product => product.id !== id
  )
}

function addToCart(product) {
  if (product.stock <= 0) {
    alert('Out of stock!')
    return
  }

  const item = cart.value.find(
    item => item.id === product.id
  )

  if (item) {
    item.quantity++
  } else {
    cart.value.push({
      id: product.id,
      name: product.name,
      price: product.price,
      quantity: 1
    })
  }

  product.stock--
}

function increaseQuantity(item) {
  const product = products.value.find(
    product => product.id === item.id
  )

  if (!product) return

  if (product.stock <= 0) {
    alert('No more stock!')
    return
  }

  item.quantity++
  product.stock--
}

function decreaseQuantity(item) {
  const product = products.value.find(
    product => product.id === item.id
  )

  if (item.quantity > 1) {
    item.quantity--

    if (product) {
      product.stock++
    }
  } else {
    removeFromCart(item.id)
  }
}

function removeFromCart(id) {
  const item = cart.value.find(
    item => item.id === id
  )

  if (!item) return

  const product = products.value.find(
    product => product.id === id
  )

  if (product) {
    product.stock += item.quantity
  }

  cart.value = cart.value.filter(
    item => item.id !== id
  )
}

const subtotal = computed(() => {
  return cart.value.reduce(
    (total, item) =>
      total + item.price * item.quantity,
    0
  )
})

const discountRate = computed(() => {
  return promoCode.value.toUpperCase() === 'SAVE20'
    ? 0.2
    : 0
})

const discount = computed(() => {
  return subtotal.value * discountRate.value
})

const grandTotal = computed(() => {
  return subtotal.value - discount.value
})

const cartCount = computed(() => {
  return cart.value.reduce(
    (total, item) => total + item.quantity,
    0
  )
})

watch(
  products,
  value => {
    localStorage.setItem(
      'products',
      JSON.stringify(value)
    )
  },
  { deep: true }
)

watch(
  cart,
  value => {
    localStorage.setItem(
      'cart',
      JSON.stringify(value)
    )
  },
  { deep: true }
)

onMounted(() => {
  const savedProducts =
    localStorage.getItem('products')

  const savedCart =
    localStorage.getItem('cart')

  if (savedProducts) {
    products.value = JSON.parse(savedProducts)
  }

  if (savedCart) {
    cart.value = JSON.parse(savedCart)
  }
})
</script>

<template>
  <div class="app">

    <Header :cart-count="cartCount" />

    <ProductCatalog
      :products="filteredProducts"
      @add-to-cart="addToCart"
      @delete-product="deleteProduct"
    />

    <AddProduct
      :new-product="newProduct"
      @add-product="addProduct"
    />

    <ShoppingCart
      :cart="cart"
      @increase="increaseQuantity"
      @decrease="decreaseQuantity"
      @remove="removeFromCart"
    />

    <CheckoutSummary
      :subtotal="subtotal"
      :discount-rate="discountRate"
      :discount="discount"
      :grand-total="grandTotal"
      :promo-code="promoCode"
      :cart-length="cart.length"
      @update-promo="promoCode = $event"
    />

  </div>
</template>
```
