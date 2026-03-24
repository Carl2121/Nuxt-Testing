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
  <div class="p-6 space-y-6">
    <!-- Header -->
    <div class="flex items-center justify-between">
      <h1 class="text-3xl font-bold">Beverages</h1>
      <div class="badge badge-primary badge-lg">
        {{ beverages?.length || 0 }} results
      </div>
    </div>

    <!-- Loading -->
    <div v-if="pending" class="grid grid-cols-1 md:grid-cols-2 gap-4">
      <div
        v-for="i in 4"
        :key="i"
        class="card bg-base-100 shadow animate-pulse p-4 space-y-3"
      >
        <div class="h-4 bg-base-300 rounded w-2/3"></div>
        <div class="h-3 bg-base-300 rounded w-1/2"></div>
        <div class="h-3 bg-base-300 rounded w-1/4"></div>
      </div>
    </div>

    <!-- Error -->
    <div v-else-if="error" class="alert alert-error shadow-lg">
      <span>Failed to load beverages.</span>
    </div>

    <!-- Empty State -->
    <div
      v-else-if="beverages?.length === 0"
      class="text-center py-16 text-base-content/60"
    >
      <div class="text-5xl mb-3">🍹</div>
      <p>No beverages found.</p>
    </div>

    <!-- Cards -->
    <div v-else class="grid grid-cols-1 md:grid-cols-2 xl:grid-cols-3 gap-6">
      <div
        v-for="drink in beverages"
        :key="drink.CustomerId"
        class="card bg-base-100 shadow-xl hover:shadow-2xl transition-all duration-300 hover:-translate-y-1"
      >
        <div class="card-body">
          <!-- Title -->
          <h2 class="card-title justify-between">
            {{ drink.CompanyName }}
            <div class="badge badge-outline">ID {{ drink.CustomerId }}</div>
          </h2>

          <!-- Content -->
          <p class="text-sm opacity-70">👤 {{ drink.ContactName }}</p>

          <!-- Actions -->
          <div class="card-actions justify-end mt-4">
            <button class="btn btn-sm btn-outline btn-primary">View</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
