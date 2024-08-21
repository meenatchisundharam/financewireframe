<template>
    <div class="max-w-4xl mx-auto p-6 bg-gray-100 rounded-lg">
  <h2 class="text-2xl font-bold mb-4">Transaction History</h2>
  
  <!-- Filter Transactions -->
  <form class="flex space-x-4 mb-4">
    <div>
      <label for="filter-date" class="block text-gray-700">Date</label>
      <input id="filter-date" type="date" class="p-2 border border-gray-300 rounded">
    </div>
    
    <div>
      <label for="filter-category" class="block text-gray-700">Category</label>
      <input id="filter-category" type="text" class="p-2 border border-gray-300 rounded" placeholder="Enter Category">
    </div>

    <div>
      <label for="filter-account" class="block text-gray-700">Account</label>
      <select id="filter-account" class="p-2 border border-gray-300 rounded">
        <option value="">All</option>
        <option value="cash">Cash</option>
        <option value="card">Card</option>
        <option value="upi">UPI</option>
      </select>
    </div>

    <button type="submit" class="bg-blue-500 text-white px-4 py-2 rounded">Filter</button>
  </form>

  <!-- Transaction History Table -->
  <table class="w-full table-auto bg-white border border-gray-300 rounded">
    <thead>
      <tr>
        <th class="px-4 py-2 border-b">Date</th>
        <th class="px-4 py-2 border-b">Type</th>
        <th class="px-4 py-2 border-b">Amount</th>
        <th class="px-4 py-2 border-b">Category</th>
        <th class="px-4 py-2 border-b">Account</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="px-4 py-2 border-b">2024-08-14</td>
        <td class="px-4 py-2 border-b">Income</td>
        <td class="px-4 py-2 border-b">$1000</td>
        <td class="px-4 py-2 border-b">Salary</td>
        <td class="px-4 py-2 border-b">Bank Transfer</td>
      </tr>
      <tr>
        <td class="px-4 py-2 border-b">2024-08-14</td>
        <td class="px-4 py-2 border-b">Expense</td>
        <td class="px-4 py-2 border-b">$100</td>
        <td class="px-4 py-2 border-b">Groceries</td>
        <td class="px-4 py-2 border-b">Card</td>
      </tr>
      <!-- Repeat rows for other transactions -->
    </tbody>
  </table>
</div>

</template>