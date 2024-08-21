<template>
    <div class="p-4">
      <form @submit.prevent="submitForm">
        <input type="date" v-model="date" class="w-full p-2 border mb-4" required>
        <input type="number" v-model="amount" class="w-full p-2 border mb-4" required>
        <select v-model="category" class="w-full p-2 border mb-4">
          <option>Category</option>
          <option value="salary">Salary</option>
          <option value="groceries">Groceries</option>
          <!-- More options... -->
        </select>
        <select v-model="account" class="w-full p-2 border mb-4">
          <option>Account</option>
          <option value="cash">Cash</option>
          <option value="card">Card</option>
          <option value="upi">UPI</option>
        </select>
        <textarea v-model="notes" class="w-full p-2 border mb-4" placeholder="Notes"></textarea>
        <button type="submit" class="bg-blue-500 text-white w-full py-2 rounded">Submit</button>
      </form>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const date = ref('');
  const amount = ref('');
  const category = ref('');
  const account = ref('');
  const notes = ref('');
  
  const submitForm = () => {
    // Handle form submission
  }
  </script>
  