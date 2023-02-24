<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <header class="bg-black w-full h-1/5">
    <img src="./assets/logo.svg" alt="logo no disponible" class="mx-auto" width="500" height="600">
  </header>

    <div class="place-content-center bg-black">
      <div class="bg-lime-400 wrapper border w-3/5 h-full text-center flex">
      <div class="w-1/3">
        <RouterLink to="/">Inicio</RouterLink>
      </div>
      <div class="w-1/3">
        <RouterLink to="/personajes">Personajes</RouterLink>
      </div>
      <div class="w-1/3">
        <RouterLink to="/about">Acerca de</RouterLink>
      </div>
    </div>
    </div>
  <RouterView />
</template>

<style scoped>

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
