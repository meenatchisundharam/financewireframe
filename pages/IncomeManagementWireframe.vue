<template>
    <div class="max-w-4xl mx-auto p-6 bg-gray-100 rounded-lg">
  <h2 class="text-2xl font-bold mb-4">Income Management</h2>
  
  <!-- Add Income Form -->
  <form class="space-y-4">
    <div>
      <label for="amount" class="block text-gray-700">Amount</label>
      <input id="amount" type="number" class="w-full p-2 border border-gray-300 rounded" placeholder="Enter Amount">
    </div>
    
    <div>
      <label for="date" class="block text-gray-700">Date</label>
      <input id="date" type="date" class="w-full p-2 border border-gray-300 rounded">
    </div>

    <div>
      <label for="category" class="block text-gray-700">Category</label>
      <input id="category" type="text" class="w-full p-2 border border-gray-300 rounded" placeholder="Enter Category">
    </div>

    <div>
      <label for="account" class="block text-gray-700">Account</label>
      <select id="account" class="w-full p-2 border border-gray-300 rounded">
        <option value="cash">Cash</option>
        <option value="card">Card</option>
        <option value="upi">UPI</option>
      </select>
    </div>

    <div>
      <label for="proof" class="block text-gray-700">Proof (optional)</label>
      <input id="proof" type="file" class="w-full p-2 border border-gray-300 rounded">
    </div>
    
    <div>
      <label for="notes" class="block text-gray-700">Notes</label>
      <textarea id="notes" class="w-full p-2 border border-gray-300 rounded" placeholder="Enter Notes"></textarea>
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
        <th class="px-4 py-2 border-b">Actions</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="px-4 py-2 border-b">2024-08-14</td>
        <td class="px-4 py-2 border-b">$1000</td>
        <td class="px-4 py-2 border-b">Salary</td>
        <td class="px-4 py-2 border-b">Bank Transfer</td>
        <td class="px-4 py-2 border-b">
          <button class="text-blue-500">Edit</button>
          <button class="text-red-500 ml-2">Delete</button>
        </td>
      </tr>
      <!-- Repeat rows for other income -->
    </tbody>
  </table>
</div>

</template>