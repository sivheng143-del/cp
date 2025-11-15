<template>
  <div class="dashboard">
    <aside class="sidebar">
      <h2>My Dashboard</h2>
      <nav>
        <ul>
          <li><a href="#">Overview</a></li>
          <li><a href="#">Analytics</a></li>
          <li><a href="#">Settings</a></li>
        </ul>
      </nav>
    </aside>

    <main class="content">
      <header>
        <h1>Dashboard Overview</h1>
      </header>
      <section class="cards">
        <div class="card">Users: 1,234</div>
        <div class="card">Sales: $12,345</div>
        <div class="card">Growth: +15%</div>
      </section>

      <section class="chart">
        <canvas id="myChart"></canvas>
      </section>
    </main>
  </div>
</template>

<script setup>
import { onMounted } from 'vue'
import Chart from 'chart.js/auto'

onMounted(() => {
  const ctx = document.getElementById('myChart')
  new Chart(ctx, {
    type: 'line',
    data: {
      labels: ['Jan', 'Feb', 'Mar', 'Apr', 'May'],
      datasets: [
        {
          label: 'Revenue',
          data: [1200, 1900, 3000, 2500, 3200],
          borderWidth: 2,
        },
      ],
    },
  })
})
</script>

<style scoped>
.dashboard {
  display: flex;
  height: 100vh;
  background: #f9fafb;
}
.sidebar {
  width: 220px;
  background: #111827;
  color: white;
  padding: 1rem;
}
.sidebar h2 {
  font-size: 1.25rem;
  margin-bottom: 1rem;
}
.sidebar ul {
  list-style: none;
  padding: 0;
}
.sidebar li {
  margin: 0.5rem 0;
}
.sidebar a {
  color: white;
  text-decoration: none;
}
.content {
  flex: 1;
  padding: 1.5rem;
}
.cards {
  display: flex;
  gap: 1rem;
  margin-bottom: 2rem;
}
.card {
  flex: 1;
  background: white;
  padding: 1rem;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}
.chart {
  background: white;
  padding: 1rem;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}
</style>
