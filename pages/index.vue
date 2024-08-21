<template>
  <div class="max-w-4xl mx-auto p-6 bg-gray-100 rounded-lg">
    <h2 class="text-2xl font-bold mb-4">Income Management</h2>

    <!-- Add Income Form -->
    <form class="space-y-4" @submit.prevent="addIncome">
      <div>
        <label for="amount" class="block text-gray-700">Amount</label>
        <input v-model="newIncome.amount" id="amount" type="number" class="w-full p-2 border border-gray-300 rounded" placeholder="Enter Amount">
      </div>

      <div class="flex space-x-4">
        <!-- Date input -->
        <div>
          <label for="date" class="block text-gray-700">Date</label>
          <input v-model="newIncome.date" id="date" type="date" class="p-2 border border-gray-300 rounded" />
        </div>

        <!-- Time input -->
        <div>
          <label for="time" class="block text-gray-700">Time</label>
          <input v-model="newIncome.time" id="time" type="time" class="p-2 border border-gray-300 rounded" />
        </div>
      </div>

      <!-- Category input with option to add new category -->
      <div>
        <label for="category" class="block text-gray-700">Category</label>
        <select v-model="newIncome.category" id="category" class="w-full p-2 border border-gray-300 rounded">
          <option v-for="category in categories" :key="category" :value="category">{{ category }}</option>
        </select>
        <input v-model="newCategory" type="text" placeholder="Add New Category" class="w-full p-2 mt-2 border border-gray-300 rounded">
        <button type="button" @click="addCategory" class="bg-green-500 text-white px-4 py-2 rounded mt-2">Add Category</button>
      </div>

      <!-- Account input with option to add new account -->
      <div>
        <label for="account" class="block text-gray-700">Account</label>
        <select v-model="newIncome.account" id="account" class="w-full p-2 border border-gray-300 rounded">
          <option v-for="account in accounts" :key="account" :value="account">{{ account }}</option>
        </select>
        <input v-model="newAccount" type="text" placeholder="Add New Account" class="w-full p-2 mt-2 border border-gray-300 rounded">
        <button type="button" @click="addAccount" class="bg-green-500 text-white px-4 py-2 rounded mt-2">Add Account</button>
      </div>

      <div>
        <label for="proof" class="block text-gray-700">Proof (optional)</label>
        <input id="proof" type="file" class="w-full p-2 border border-gray-300 rounded" @change="handleFileUpload">
      </div>

      <div>
        <label for="notes" class="block text-gray-700">Notes</label>
        <textarea v-model="newIncome.notes" id="notes" class="w-full p-2 border border-gray-300 rounded" placeholder="Enter Notes"></textarea>
      </div>

      <button type="submit" class="bg-blue-500 text-white px-4 py-2 rounded">Add Income</button>
    </form>

    <!-- Income History Table -->
    <h3 class="text-xl font-bold mt-8 mb-4">Income History</h3>
    <table class="w-full table-auto bg-white border border-gray-300 rounded">
      <thead>
        <tr>
          <th class="px-4 py-2 border-b">Date</th>
          <th class="px-4 py-2 border-b">Amount</th>
          <th class="px-4 py-2 border-b">Category</th>
          <th class="px-4 py-2 border-b">Account</th>
          <th class="px-4 py-2 border-b">Proof</th>
          <th class="px-4 py-2 border-b">Actions</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(income, index) in incomes" :key="index">
          <td class="px-4 py-2 border-b">{{ income.date }} {{ income.time }}</td>
          <td class="px-4 py-2 border-b">{{ income.amount }}</td>
          <td class="px-4 py-2 border-b">{{ income.category }}</td>
          <td class="px-4 py-2 border-b">{{ income.account }}</td>
          <td class="px-4 py-2 border-b">
            <a v-if="income.proof" :href="income.proofUrl" target="_blank" class="text-blue-500">View Proof</a>
            <span v-else class="text-gray-500">No Proof</span>
          </td>
          <td class="px-4 py-2 border-b">
            <button @click="editIncome(index)" class="text-blue-500">Edit</button>
            <button @click="deleteIncome(index)" class="text-red-500 ml-2">Delete</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>


<script setup>
import { ref, onMounted } from 'vue'

// Initial categories and accounts
const categories = ref(['Salary', 'Allowance', 'Pettycash'])
const accounts = ref(['Cash', 'Card', 'UPI'])

const incomes = ref([])
const newIncome = ref({
  amount: '',
  date: '',
  time: '',
  category: categories.value[0], // Default to the first category
  account: accounts.value[0], // Default to the first account
  proof: null,
  proofUrl: '',
  notes: ''
})

const newCategory = ref('')
const newAccount = ref('')

onMounted(() => {
  const now = new Date()

  const year = now.getFullYear()
  const month = String(now.getMonth() + 1).padStart(2, '0')
  const day = String(now.getDate()).padStart(2, '0')
  newIncome.value.date = `${year}-${month}-${day}`

  const hours = String(now.getHours()).padStart(2, '0')
  const minutes = String(now.getMinutes()).padStart(2, '0')
  newIncome.value.time = `${hours}:${minutes}`
})

// Add a new income record
function addIncome() {
  // If proof is provided, create a URL for it
  if (newIncome.value.proof) {
    const proofUrl = URL.createObjectURL(newIncome.value.proof)
    newIncome.value.proofUrl = proofUrl
  }
  
  incomes.value.push({ ...newIncome.value })
  resetForm()
}

// Reset form to initial state
function resetForm() {
  newIncome.value = {
    amount: '',
    date: newIncome.value.date,
    time: newIncome.value.time,
    category: categories.value[0],
    account: accounts.value[0],
    proof: null,
    proofUrl: '',
    notes: ''
  }
}

// Delete a specific income record
function deleteIncome(index) {
  incomes.value.splice(index, 1)
}

// Edit a specific income record
function editIncome(index) {
  const income = incomes.value[index]
  newIncome.value = { ...income }
  deleteIncome(index)
}

// Handle file upload for proof
function handleFileUpload(event) {
  const file = event.target.files[0]
  if (file) {
    newIncome.value.proof = file
  }
}

// Add a new category to the categories list
function addCategory() {
  if (newCategory.value && !categories.value.includes(newCategory.value)) {
    categories.value.push(newCategory.value)
    newCategory.value = ''
  }
}

// Add a new account to the accounts list
function addAccount() {
  if (newAccount.value && !accounts.value.includes(newAccount.value)) {
    accounts.value.push(newAccount.value)
    newAccount.value = ''
  }
}
</script>
