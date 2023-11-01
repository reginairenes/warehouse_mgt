<script>
    import Grid from "gridjs-svelte";
    // import '../app.postcss';

  
    // Define your dummy data as an array of objects
    const dummyData = [
      { id: 1, type: 'take a chance', produk: 'Product A', status: 'In Progress', tracking: '12345', picking: 'Picking A', picking_status: 'FIFO' },
      { id: 2, type: 'oceans and', produk: 'Product B', status: 'Completed', tracking: '67890', picking: 'Picking B', picking_status: 'FIFO' },
      { id: 3, type: 'engines', produk: 'Product A', status: 'Pending', tracking: '12345', picking: 'Picking A', picking_status: 'FIFO' },
      { id: 4, type: 'Taylor', produk: 'Product B', status: 'Completed', tracking: '67890', picking: 'Picking B', picking_status: 'FIFO' },
      { id: 5, type: 'niki', produk: 'Product A', status: 'In Progress', tracking: '12345', picking: 'Picking A', picking_status: 'FIFO' },
      { id: 6, type: 'slank ', produk: 'Product B', status: 'Pending', tracking: '67890', picking: 'Picking B', picking_status: 'FIFO' },
      { id: 7, type: 'ipank', produk: 'Product A', status: 'In Progress', tracking: '12345', picking: 'Picking A', picking_status: 'FIFO' },
      { id: 8, type: 'iwan ', produk: 'Product B', status: 'Completed', tracking: '67890', picking: 'Picking B', picking_status: 'FIFO' },
      { id: 9, type: 'yusron jelek', produk: 'Product A', status: 'In Progress', tracking: '12345', picking: 'Picking A', picking_status: 'FIFO' },
      { id: 10, type: 'nisa', produk: 'Product B', status: 'Pending', tracking: '67890', picking: 'Picking B', picking_status: 'FIFO' },
      { id: 11, type: 'khalfan', produk: 'Product A', status: 'In Progress', tracking: '12345', picking: 'Picking A', picking_status: 'FIFO' },
      { id: 12, type: 'reere', produk: 'Product B', status: 'Completed', tracking: '67890', picking: 'Picking B', picking_status: 'FIFO' },
      { id: 13, type: 'anin', produk: 'Product A', status: 'In Progress', tracking: '12345', picking: 'Picking A', picking_status: 'FIFO' },
      { id: 14, type: 'marina', produk: 'Product B', status: 'Pending', tracking: '67890', picking: 'Picking B', picking_status: 'FIFO' },
      { id: 15, type: 'salsa', produk: 'Product A', status: 'In Progress', tracking: '12345', picking: 'Picking A', picking_status: 'FIFO' },
      { id: 16, type: 'anisaops', produk: 'Product B', status: 'Completed', tracking: '67890', picking: 'Picking B', picking_status: 'FIFO' },
      { id: 17, type: 'hanif', produk: 'Product A', status: 'Pending', tracking: '12345', picking: 'Picking A', picking_status: 'FIFO' },
      { id: 18, type: 'dumu', produk: 'Product B', status: 'Completed', tracking: '67890', picking: 'Picking B', picking_status: 'FIFO' },
    ];
  
    const columns = [
      {
        name: 'id',
        sort: true // Enable sorting for the 'id' column
      },
      {
        name: 'type',
        sort: true // Enable sorting for the 'type' column
      },
      {
        name: 'produk',
        sort: true // Enable sorting for the 'produk' column
      },
      {
        name: 'status',
        sort: true // Enable sorting for the 'status' column
      },
      {
        name: 'tracking',
        sort: true // Enable sorting for the 'tracking' column
      },
      {
        name: 'picking',
        sort: true // Enable sorting for the 'picking' column
      },
      {
        name: 'picking_status',
        sort: true // Enable sorting for the 'picking strategy' column
      },
    ];
  </script>
  
  <div class="my-grid">
    <Grid
      {columns}
      sort
      search
      pagination={{ enabled: true, limit: 7}}
      data={dummyData}
    />
  </div>
  
  <style global>
    @import "https://cdn.jsdelivr.net/npm/gridjs/dist/theme/mermaid.min.css";
  </style>