<template>
    <aside
      :class="['fixed z-50 inset-0 bg-gray-900 bg-opacity-50', menuVisible ? 'block' : 'hidden']"
    >
      <nav class="bg-white p-4 w-64 space-y-4">
        <nuxt-link to="/" class="block">Home</nuxt-link>
        <nuxt-link to="/income" class="block">Income Management</nuxt-link>
        <nuxt-link to="/expenses" class="block">Expense Management</nuxt-link>
        <!-- More links... -->
        <button @click="logout" class="text-red-500">Logout</button>
      </nav>
    </aside>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const menuVisible = ref(false);
  
  const toggleMenu = () => {
    menuVisible.value = !menuVisible.value;
  }
  
  const logout = () => {
    // Logout function
  }
  </script>
  