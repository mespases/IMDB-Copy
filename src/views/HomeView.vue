<script setup>
  import FilmCard from '../components/FilmCard.vue';
  import jsonData from '@/assets/json/films.json'

  const items = [{'title': 1}, {'title': 1}, {'title': 1}, {'title': 1}, {'title': 1}, {'title': 1}, {'title': 1}, {'title': 1}, {'title': 1}, {'title': 1}]
</script>

<template>
  <section class="all_movies">
    <FilmCard v-for="item in jsonData" :key="item.id" :item="item"/>
  </section>
</template>

<style scoped>

</style>
