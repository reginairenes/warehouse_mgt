<script>
  // Import your data or define sample data here
  let data = [
    { title: 'Total Items', value: 1000 },
    { title: 'Pending Orders', value: 25 },
    { title: 'Inventory Value', value: '$50,000' },
  ];
</script>

<style>
  /* Add your custom styles here */
  .dashboard-card {
    transition: background-color 0.3s ease;
  }
 
  .dashboard-card:hover {
    background-color: #cac5c5; /* Change to your desired hover background color */
  }
</style>

<div class="min-h-screen p-5">
  <!-- Sidebar -->
  <aside class="w-64 bg-white shadow">
    <!-- Sidebar content -->
    <!-- You can add links and navigation here -->
  </aside>

  <!-- Main content -->
  <main class="flex-1 p-2">
    <!-- Header -->
    <header class="mb-2">
      <h1 class="text-2xl font-semibold">Dashboard</h1>
    </header>

    <!-- Dashboard Cards -->
    <section class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
      {#each data as item (item.title)}
        <div class="p-4 bg-gray-100 shadow rounded-lg dashboard-card"> <!-- Change bg-white to bg-gray-200 -->
          <h2 class="text-lg font-semibold mb-2">{item.title}</h2>
          <p class="text-gray-700">{item.value}</p>
        </div>
      {/each}
    </section>
  </main>
</div>
