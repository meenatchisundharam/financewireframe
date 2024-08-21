<template>
    <div class="max-w-4xl mx-auto p-6 bg-gray-100 rounded-lg">
  <h2 class="text-2xl font-bold mb-4">Budget Planner</h2>
  
  <!-- Add Budget Form -->
  <form class="space-y-4">
    <div>
      <label for="start_date" class="block text-gray-700">Start Date</label>
      <input id="start_date" type="date" class="w-full p-2 border border-gray-300 rounded">
    </div>
    
    <div>
      <label for="end_date" class="block text-gray-700">End Date</label>
      <input id="end_date" type="date" class="w-full p-2 border border-gray-300 rounded">
    </div>

    <div>
      <label for="total_budget" class="block text-gray-700">Total Budget</label>
      <input id="total_budget" type="number" class="w-full p-2 border border-gray-300 rounded" placeholder="Enter Total Budget">
    </div>
    
    <div>
      <label for="allocated_budget" class="block text-gray-700">Allocated Budget</label>
      <input id="allocated_budget" type="number" class="w-full p-2 border border-gray-300 rounded" placeholder="Enter Allocated Budget">
    </div>
    
    <button type="submit" class="bg-yellow-500 text-white px-4 py-2 rounded">Create Budget</button>
  </form>
  
  <!-- Budget History Table -->
  <h3 class="text-xl font-bold mt-8 mb-4">Budget Plans</h3>
  <table class="w-full table-auto bg-white border border-gray-300 rounded">
    <thead>
      <tr>
        <th class="px-4 py-2 border-b">Start Date</th>
        <th class="px-4 py-2 border-b">End Date</th>
        <th class="px-4 py-2 border-b">Total Budget</th>
        <th class="px-4 py-2 border-b">Allocated Budget</th>
        <th class="px-4 py-2 border-b">Actions</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="px-4 py-2 border-b">2024-08-01</td>
        <td class="px-4 py-2 border-b">2024-08-31</td>
        <td class="px-4 py-2 border-b">$5000</td>
        <td class="px-4 py-2 border-b">$4500</td>
        <td class="px-4 py-2 border-b">
          <button class="text-blue-500">Edit</button>
          <button class="text-red-500 ml-2">Delete</button>
        </td>
      </tr>
      <!-- Repeat rows for other budgets -->
    </tbody>
  </table>
</div>

</template>