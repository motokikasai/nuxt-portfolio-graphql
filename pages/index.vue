<script setup>
const { data: home } = await useAsyncData(() =>
  queryCollection("content").path("/").first()
);
</script>

<template>
  <!-- <h2>Hello World!</h2>
  <div>We are on the roll, <a href="#" class="italic">baby!</a>🕺</div> -->
  <ContentRenderer v-if="home" :value="home" />
  <div v-else>Home not found</div>
</template>
