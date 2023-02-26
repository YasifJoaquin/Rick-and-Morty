<script>
import axios from 'axios'

let API_URL = 'https://rickandmortyapi.com/api/character'

export default {

  data() {
    return {
      info: [],
      personajes: [],
      cont:2,
      search: "",
    }
  },

  mounted() {
    axios.get(API_URL)
      .then((response) => {
        this.info = response.data.info;
        this.personajes = response.data.results;
      })
  },

  methods: {
    pag(num) {
      API_URL='https://rickandmortyapi.com/api/character/?page='+num
      console.log(API_URL)
      axios.get(API_URL)
      .then((response) => {
        console.log(response.config)
        this.info = response.data.info;
        this.personajes = response.data.results;
      })
      this.cont++
    }
  },

}

</script>

<template bg-red-400>
  <div class="flex justify-center">
  <button class="border border-lime-400 bg-teal-600 px-3 text-2xl text-black font-medium rounded-l-lg m-3"> Prev </button>
  <input type="text" v.model="search" class="border border-teal-600 bg-lime-500 px-3 text-xl text-black font-medium rounded-full m-3">
  <button class="border border-lime-400 bg-teal-600 px-3 text-2xl text-black font-medium rounded-r-lg m-3"> Next </button>
  </div>

  <div class="border border-lime-500 w-2/5 h-screen text-center">
    <h2>Hay {{ info.count }} personajes en el programa de Rick & Morty</h2>
    <button @click="pag(cont)">página {{ cont }}</button> <br>
    <ul class="list-disc">
      <li v-for="p in personajes">
        <a >{{ p.name }} id:{{ p.id }}</a> 
      </li>
    </ul>
  </div>
</template>