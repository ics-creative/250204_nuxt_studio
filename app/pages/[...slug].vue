<script setup lang="ts">
const route = useRoute()

const {data: page} = await useAsyncData('page-' + route.path, () => {
  return queryCollection('content').path(route.path).first()
})

if (!page.value) {
  throw createError({statusCode: 404, statusMessage: 'Page not found', fatal: true})
}
</script>

<template>
  <div>
    <Header/>
    <p v-if="page?.date">{{ page.date }}</p>
    <ContentRenderer v-if="page" :value="page"/>
  </div>
</template>
