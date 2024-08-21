<template>
    <header class="flex items-center justify-between p-4 bg-blue-500 text-white">
      <button @click="toggleMenu" class="hamburger-menu md:hidden">☰</button>
      <h1 class="text-lg font-bold">FinanceApp</h1>
      <nuxt-link to="/profile" class="profile-icon">👤</nuxt-link>
    </header>
  </template>
  
  <script setup>
  const toggleMenu = () => {
    // Toggle mobile menu visibility
  }
  </script>
  