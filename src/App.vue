<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <header class="bg-lime-500 w-full h-40">
    <img src="./assets/logo.svg" alt="logo no disponible" class="w-96 h-40 mx-auto">
  </header>

  <div class="bg-red-400">
    <div class="wrapper border border border-solid border-8 border-black w-full h-full">
    <nav>
      <RouterLink to="/">Inicio</RouterLink>
      <RouterLink to="/personajes">Personajes</RouterLink>
      <RouterLink to="/about">Acerca de</RouterLink>
    </nav>
  </div>
  </div>
  <RouterView />
</template>

<style scoped>
div{
  color: yellow;
}

header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}

</style>
