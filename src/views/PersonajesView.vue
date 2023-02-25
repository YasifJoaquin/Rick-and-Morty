<script setup>
import Personajes from "../components/Personajes.vue";
</script>

<template>
  <div class="fondo about">
    <h1 class="text-center text-5xl pt-6 italic">Personajes del programa</h1>

    <Personajes />
  </div>
  <RouterView />
</template>

<style>
  .fondo{
    background-image: url("../assets/fondo.jpg");
    background-size: cover;
    width: 100%;
    height: 100%;
    color: yellow;
  }
  .about {
    min-height: 80vh;
    
  }
</style>
