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
      dato:"",
      detalle_personajes: []
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
    },

    prev(num) {
      API_URL='https://rickandmortyapi.com/api/character/?page='+num
      console.log(API_URL)
      axios.get(API_URL)
      .then((response) => {
        console.log(response.config)
        this.info = response.data.info;
        this.personajes = response.data.results;
      })
      this.cont--
    },

    buscando(search) {
      API_URL='https://rickandmortyapi.com/api/character/?name='+search
      console.log(API_URL)
      axios.get(API_URL)
      .then((response) => {
        console.log(response.config)
        this.info = response.data.info;
        this.personajes = response.data.results;
      })
    },

    datosp(id) {
      API_URL='https://rickandmortyapi.com/api/character/'+id
      console.log(API_URL)
      axios.get(API_URL)
      .then((response) => {
        console.log(response.config)
        this.detalle_personajes = response.data;
        console.log(this.detalle_personajes)
      })
      this.cont++

    }
  }

}

</script>

<template bg-red-400>
  <div class="flex justify-center">
  <button v-if="cont > 2" @click="prev(cont)" class="border border-lime-400 bg-teal-600 px-3 text-2xl text-black font-medium rounded-l-lg m-3"> Prev </button>
  <input type="text" v-model="search" @input="buscando(search)" class="border border-teal-600 bg-lime-500 px-3 text-xl text-black font-medium rounded-full m-3">
  <button v-if="cont < 43" @click="pag(cont)" class="border border-lime-400 bg-teal-600 px-3 text-2xl text-black font-medium rounded-r-lg m-3"> Next </button>
  </div>

  <div class="flex">
    <div class="border border-lime-500 w-2/5 h-screen text-center">
    <h2>pagina siguiente {{ cont }}</h2>
    <ul class="list-disc">
      <li v-for="p in personajes">
        <button @click="datosp(p.id)">{{ p.name }} id:{{ p.id }}</button> 
      </li>
    </ul>
  </div >

  <ul>
    <li>
      <div class="bg-white shadow-md rounded-lg max-w-sm">
        <img class="rounded-t-lg" v-bind:src="detalle_personajes.image" alt="">
        <div class="p-5 bg-lime-500">
          <h5 class="text-gray-900 font-bold text-2xl tracking-tight mb-2"> {{ detalle_personajes.name }} </h5>
          <p class="font-normal text-gray-700 text-justify">Estado: {{ detalle_personajes.status }}</p>
          <p class="font-normal text-gray-700 text-justify">Especie: {{ detalle_personajes.species }}</p>
          <p class="font-normal text-gray-700 text-justify">Genero: {{ detalle_personajes.gender }}</p>
        </div>
      </div>
    </li>
  </ul>
  </div>

</template>

