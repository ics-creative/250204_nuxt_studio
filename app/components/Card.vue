<script setup lang="ts">
const props = defineProps<{
  image: string;
}>();
</script>

<template>
  <div class="card">
    <div>
      <img :src="props.image" alt=""/>
    </div>
    <p class="title">
      <slot name="title" mdc-unwrap="p" />
    </p>
    <p class="description">
      <slot mdc-unwrap="p"/>
    </p>
  </div>
</template>

<style scoped>
.card {
  width: 200px;
  height: auto;
  display: grid;
  grid-template-rows: 150px max-content 1fr;
  border: 1px solid #ccc;
  gap: 0.5rem;
  padding: 0 0 0.5rem 0;
}

.card img {
  object-fit: cover;
  width: 100%;
  height: 100%;
}

.card .title {
  font-size: 1.2rem;
  font-weight: bold;
  margin: 0;
  padding: 0 0.5rem;
  margin: 0;
}

.card .description {
  margin: 0;
  padding: 0 0.5rem;
}



</style>
