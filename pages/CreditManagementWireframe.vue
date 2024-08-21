<template>
    <div class="max-w-4xl mx-auto p-6 bg-gray-100 rounded-lg">
  <h2 class="text-2xl font-bold mb-4">Credit Management</h2>
  
  <!-- Add Credit Form -->
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
      <label for="description" class="block text-gray-700">Description</label>
      <textarea id="description" class="w-full p-2 border border-gray-300 rounded" placeholder="Enter Description"></textarea>
    </div>
    
    <div>
      <label for="proof" class="block text-gray-700">Proof (optional)</label>
      <input id="proof" type="file" class="w-full p-2 border border-gray-300 rounded">
    </div>
    
    <button type="submit" class="bg-blue-500 text-white px-4 py-2 rounded">Add Credit</button>
  </form>
  
  <!-- Credit History Table -->
  <h3 class="text-xl font-bold mt-8 mb-4">Credit History</h3>
  <table class="w-full table-auto bg-white border border-gray-300 rounded">
    <thead>
      <tr>
        <th class="px-4 py-2 border-b">Date</th>
        <th class="px-4 py-2 border-b">Amount</th>
        <th class="px-4 py-2 border-b">Description</th>
        <th class="px-4 py-2 border-b">Actions</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="px-4 py-2 border-b">2024-08-14</td>
        <td class="px-4 py-2 border-b">$500</td>
        <td class="px-4 py-2 border-b">Loan from friend</td>
        <td class="px-4 py-2 border-b">
          <button class="text-blue-500">Edit</button>
          <button class="text-red-500 ml-2">Delete</button>
        </td>
      </tr>
      <!-- Repeat rows for other credits -->
    </tbody>
  </table>
</div>

</template>