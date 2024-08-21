<template>
    <!-- Mobile View Wireframe -->
<div class="min-h-screen flex flex-col bg-gray-100">

<!-- Header -->
<header class="flex items-center justify-between p-4 bg-blue-500 text-white">
  <button class="hamburger-menu">☰</button>
  <h1 class="text-lg font-bold">FinanceApp</h1>
  <button class="profile-icon">👤</button>
</header>

<!-- Content Area -->
<main class="flex-1 overflow-y-auto p-4">
  
  <!-- Dashboard -->
  <section id="dashboard" class="space-y-4">
    <div class="summary-grid grid grid-cols-3 gap-4">
      <div class="bg-white p-4 rounded shadow">
        <p class="text-sm">Income</p>
        <p class="text-lg font-bold">$1200</p>
      </div>
      <div class="bg-white p-4 rounded shadow">
        <p class="text-sm">Expense</p>
        <p class="text-lg font-bold">$800</p>
      </div>
      <div class="bg-white p-4 rounded shadow">
        <p class="text-sm">Savings</p>
        <p class="text-lg font-bold">$400</p>
      </div>
    </div>
    <div class="quick-actions grid grid-cols-2 gap-4">
      <button class="bg-green-500 text-white p-4 rounded">Add Income</button>
      <button class="bg-red-500 text-white p-4 rounded">Add Expense</button>
    </div>
    <div class="recent-transactions bg-white p-4 rounded shadow">
      <h2 class="text-lg font-bold mb-2">Recent Transactions</h2>
      <ul class="space-y-2">
        <li class="flex justify-between">
          <span>Salary</span>
          <span>$1000</span>
        </li>
        <li class="flex justify-between">
          <span>Groceries</span>
          <span>-$50</span>
        </li>
        <!-- More transactions... -->
      </ul>
      <button class="text-blue-500 mt-4">View All Transactions</button>
    </div>
  </section>
  
  <!-- Add Income/Expense Form -->
  <section id="add-income" class="hidden space-y-4">
    <div class="bg-white p-4 rounded shadow">
      <h2 class="text-lg font-bold mb-4">Add Income</h2>
      <form class="space-y-4">
        <input type="date" class="w-full p-2 border border-gray-300 rounded" placeholder="Date">
        <input type="number" class="w-full p-2 border border-gray-300 rounded" placeholder="Amount">
        <select class="w-full p-2 border border-gray-300 rounded">
          <option>Category</option>
          <!-- Options... -->
        </select>
        <select class="w-full p-2 border border-gray-300 rounded">
          <option>Account</option>
          <!-- Options... -->
        </select>
        <textarea class="w-full p-2 border border-gray-300 rounded" placeholder="Notes"></textarea>
        <input type="file" class="w-full p-2 border border-gray-300 rounded">
        <button type="submit" class="bg-blue-500 text-white w-full py-2 rounded">Submit</button>
      </form>
    </div>
  </section>
  
  <!-- Similar sections for Credit Management, Savings Tracking, etc... -->
  
</main>

<!-- Navigation Menu -->
<nav class="fixed bottom-0 left-0 right-0 bg-white shadow flex justify-around p-4">
  <button class="text-blue-500">Home</button>
  <button class="text-gray-500">Income</button>
  <button class="text-gray-500">Expenses</button>
  <button class="text-gray-500">Transactions</button>
  <button class="text-gray-500">Settings</button>
</nav>

</div>

</template>