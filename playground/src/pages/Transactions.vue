<script>
import DefaultLayout from '../layouts/DefaultLayout.vue'

export default {
  components: {
    DefaultLayout
  }
}
</script>

<template>
  <DefaultLayout>
    <h1>🧾 Transactions Page</h1>
    <hr />
    <div class="transaction-grid">
      <section>
        <h2>New Transaction</h2>
        <form @submit.prevent>
          <div class="base-input-wrapper">
            <label for="transaction-date" class="base-input-label">
              Purchase Date
            </label>
            <input type="date" id="transaction-date" class="base-input" />
          </div>
          <div class="base-input-wrapper">
            <label for="transaction-title" class="base-input-label">
              Title
            </label>
            <input type="text" id="transaction-title" class="base-input" />
          </div>
          <div class="base-input-wrapper">
            <label for="transaction-estimate" class="base-input-label">
              Cost
            </label>
            <input
              type="number"
              step="0.01"
              placeholder="0.00"
              id="transaction-estimate"
              class="base-input"
            />
          </div>
          <button class="base-button">Add New Transaction</button>
        </form>
      </section>
      <section>
        <h2>Metrics</h2>
        <div class="metrics-grid">
          <div class="metric">
            <h3>Total Transactions</h3>
            <p class="metric-number">2</p>
          </div>
          <div class="metric">
            <h3>Total Cost</h3>
            <p class="metric-number">$30</p>
          </div>
          <div class="metric">
            <h3>Average Cost</h3>
            <p class="metric-number">$15</p>
          </div>
        </div>
        <h2>Existing Transactions</h2>
        <table class="transaction-table">
          <thead>
            <tr>
              <th>Purchased On</th>
              <th>Title</th>
              <th>Cost</th>
              <th>Actions</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td class="text-center">2021-11-01</td>
              <td>Item #1</td>
              <td class="text-center">$10.00</td>
              <td class="text-center"><button>Edit</button></td>
            </tr>
            <tr>
              <td class="text-center">2021-11-02</td>
              <td>Item #2</td>
              <td class="text-center">$20.00</td>
              <td class="text-center"><button>Edit</button></td>
            </tr>
          </tbody>
        </table>
      </section>
    </div>
  </DefaultLayout>
</template>

<style>
.base-button {
  padding: 0.25rem 0.5rem;
}

.base-input {
  display: flex;
  width: 100%;
  padding: 0.25rem;
}

.base-input-label {
  display: block;
  margin-bottom: 0.5rem;
}

.base-input-wrapper {
  margin-bottom: 1rem;
}

.metrics-grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-gap: 1rem;
  margin-bottom: 2rem;
}

.metrics-grid .metric {
  border: 2px solid #222;
  padding: 1rem;
  text-align: center;
}

.metrics-grid .metric-number {
  font-size: 2rem;
  font-weight: 300;
}

.transaction-grid {
  display: grid;
  grid-template-columns: 1fr 3fr;
  grid-gap: 2rem;
}

.transaction-table,
.transaction-table th,
.transaction-table td {
  width: 100%;
  border: 1px solid #222;
}

.transaction-table tr {
  display: grid;
  grid-template-columns: 1fr 2fr 1fr 1fr;
}

.text-center {
  text-align: center;
}
</style>
