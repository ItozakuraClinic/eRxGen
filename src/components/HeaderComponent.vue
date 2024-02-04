<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <nav class="flex flex-justify-between w-lg m-a my-4">
    <RouterLink class="px-4" to="/">Home</RouterLink>
    <RouterLink class="px-4" to="/about">About</RouterLink>
  </nav>
  <RouterView />
</template>