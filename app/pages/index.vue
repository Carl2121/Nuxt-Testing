<script setup>
const {
  data: beverages,
  pending,
  error,
} = await useFetch(
  "https://d1-tutorial.herederocarlos9.workers.dev/api/beverages",
);
</script>

<template>
  <div class="p-6">
    <h1 class="text-2xl font-bold mb-4">Beverages</h1>

    <div v-if="pending">Loading...</div>
    <div v-else-if="error">Error loading data</div>

    <div v-else class="grid grid-cols-1 md:grid-cols-2 gap-4">
      <div
        v-for="drink in beverages"
        :key="drink.CustomerId"
        class="card bg-base-100 shadow-xl p-4"
      >
        <h2 class="text-lg font-bold">
          {{ drink.CompanyName }}
        </h2>

        <p class="text-sm opacity-70">Contact: {{ drink.ContactName }}</p>

        <p class="text-xs mt-2">ID: {{ drink.CustomerId }}</p>
      </div>
    </div>
  </div>
</template>
