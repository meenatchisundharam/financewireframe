<template>
    <div class="flex justify-center items-center h-screen bg-gray-100">
      <div class="bg-white p-6 rounded shadow-lg w-full max-w-sm">
        <h1 class="text-2xl font-bold mb-6">Login</h1>
        <form @submit.prevent="login">
          <input type="email" v-model="email" class="w-full p-2 border mb-4" placeholder="Email" required>
          <input type="password" v-model="password" class="w-full p-2 border mb-4" placeholder="Password" required>
          <button type="submit" class="bg-blue-500 text-white w-full py-2 rounded">Login</button>
        </form>
        <nuxt-link to="/forgot-password" class="text-blue-500 block text-center mt-4">Forgot Password?</nuxt-link>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const email = ref('');
  const password = ref('');
  
  const login = () => {
    // Handle login logic
  }
  </script>
  