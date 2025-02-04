<script setup lang="ts">
const {data} = await useAsyncData("header", () =>
    queryCollectionNavigation("content"),
);
</script>

<template>
  <ul>
    <li v-for="link in data" :key="link.path">
      <NuxtLink :to="link.path">{{ link.title }}</NuxtLink>
    </li>
  </ul>
</template>

<style scoped>
ul {
  list-style: none;
  display: flex;
  gap: 1rem;
  font-size: 1.25rem;
  padding: 0;
}
</style>
