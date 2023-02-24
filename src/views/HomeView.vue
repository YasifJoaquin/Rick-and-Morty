<script setup>
import TheWelcome from '../components/TheWelcome.vue'
</script>

<template>
  <main class="fondo about">
    <TheWelcome />
  </main>
</template>

<style>
  .about {
    min-height: 80vh;
    
  }

  .fondo{
    background-image: url("../assets/fondo.png");
    background-size: cover;
    width: 100%;
    height: 100%;
    color: yellow;
  }
</style>