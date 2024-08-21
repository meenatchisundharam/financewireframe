<template>
    <div class="p-4">
      <!-- Filter Transactions -->
      <form @submit.prevent="filterTransactions" class="flex flex-col md:flex-row space-y-4 md:space-x-4 mb-4">
        <input type="date" v-model="filterDate" class="p-2 border">
        <input type="text" v-model="filterCategory" class="p-2 border" placeholder="Category">
        <select v-model="filterAccount" class="p-2 border">
          <option value="">All Accounts</option>
          <option value="cash">Cash</option>
          <option value="card">Card</option>
          <option value="upi">UPI</option>
        </select>
        <button type="submit" class="bg-blue-500 text-white px-4 py-2 rounded">Filter</button>
      </form>
  
      <!-- Transactions List -->
      <div class="bg-white p-4 rounded shadow">
        <h2 class="text-lg font-bold mb-2">Transaction History</h2>
        <ul class="space-y-2">
          <li v-for="transaction in transactions" :key="transaction.id" class="flex justify-between">
            <span>{{ transaction.category }}</span>
            <span>{{ transaction.amount }}</span>
          </li>
          <!-- More transactions... -->
        </ul>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const filterDate = ref('');
  const filterCategory = ref('');
  const filterAccount = ref('');
  const transactions = ref([]);
  
  const filterTransactions = () => {
    // Filter transactions based on the criteria
  }
  </script>
  