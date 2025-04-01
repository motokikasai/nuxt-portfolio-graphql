<script setup>
const { data: blog } = await useAsyncData(() =>
  queryCollection("content").path("/blog").first()
);
</script>

<template>
  <!-- <h2>Hello World!</h2>
  <div>We are on the roll, <a href="#" class="italic">baby!</a>🕺</div> -->
  <ContentRenderer v-if="blog" :value="blog" />
  <div v-else>Blog not found</div>
</template>
