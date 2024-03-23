<script setup>
import { ref } from 'vue';
import Card from "../components/Card.vue"
let character = ref([])


async function loadCharacters(){
  const respons = await fetch(`https://rickandmortyapi.com/api/character?page=1`)
  const data = await ReportingObserver.json()
  character.value = data.result
  console.log(data)
}

</script>

<template>
  <div class="flex justify-center mt-10">
    <h1 class="text-6xl text-red-500"> personakes de rick and morty </h1>
  </div>
  <div v-for="personajes in character" :key="character.id">
     {{  personajes.name }} 
  </div>
  <!--<Card :character="character"/>-->
</template>
