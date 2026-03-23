<template>
  <div class="min-h-screen flex bg-base-200">
    <!-- Sidebar Skeleton -->
    <aside class="w-64 p-4 space-y-4 hidden md:block bg-base-100">
      <div class="skeleton h-8 w-3/4"></div>
      <div class="space-y-2 mt-6">
        <div class="skeleton h-6 w-full"></div>
        <div class="skeleton h-6 w-full"></div>
        <div class="skeleton h-6 w-full"></div>
        <div class="skeleton h-6 w-full"></div>
      </div>
    </aside>

    <!-- Main Content -->
    <div class="flex-1 flex flex-col">
      <!-- Navbar Skeleton -->
      <div class="navbar bg-base-100 shadow px-6">
        <div class="flex-1">
          <div class="skeleton h-6 w-32"></div>
        </div>
        <div class="flex gap-2 items-center">
          <div class="skeleton h-8 w-8 rounded-full"></div>
          <div class="skeleton h-6 w-24"></div>
        </div>
      </div>

      <!-- Page Content -->
      <main class="p-6 space-y-6">
        <!-- Header -->
        <div class="skeleton h-8 w-1/3"></div>

        <!-- Stats -->
        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
          <div class="card bg-base-100 shadow p-4 space-y-3">
            <div class="skeleton h-5 w-1/2"></div>
            <div class="skeleton h-10 w-full"></div>
          </div>
          <div class="card bg-base-100 shadow p-4 space-y-3">
            <div class="skeleton h-5 w-1/2"></div>
            <div class="skeleton h-10 w-full"></div>
          </div>
          <div class="card bg-base-100 shadow p-4 space-y-3">
            <div class="skeleton h-5 w-1/2"></div>
            <div class="skeleton h-10 w-full"></div>
          </div>
        </div>

        <!-- Chart Skeleton -->
        <div class="card bg-base-100 shadow p-6 space-y-4">
          <div class="skeleton h-6 w-1/4"></div>
          <div class="skeleton h-48 w-full"></div>
        </div>

        <!-- Table Skeleton -->
        <div class="card bg-base-100 shadow p-6 space-y-4">
          <div class="skeleton h-6 w-1/4"></div>

          <div class="overflow-x-auto">
            <table class="table w-full">
              <thead>
                <tr>
                  <th><div class="skeleton h-4 w-16"></div></th>
                  <th><div class="skeleton h-4 w-20"></div></th>
                  <th><div class="skeleton h-4 w-20"></div></th>
                  <th><div class="skeleton h-4 w-16"></div></th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="i in 5" :key="i">
                  <td><div class="skeleton h-4 w-full"></div></td>
                  <td><div class="skeleton h-4 w-full"></div></td>
                  <td><div class="skeleton h-4 w-full"></div></td>
                  <td><div class="skeleton h-4 w-12"></div></td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </main>
    </div>
  </div>
</template>
