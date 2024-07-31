<script>
import { store } from './store.js' //importo il file store.js
import axios from 'axios';

export default {
  data() {
    store
  },
  created() {
    this.getCards();
  },
  methods: {
    //creo una funzione per popolare l'array che conterrà le carte all'interno di store.js
    getCards() {
      axios.get(store.apiUrl).then((data) => {
        store.cardsList = data.data;
        //console.log(store.cardsList)
      })
    },
  },
}
</script>

<template>
  <div>

  </div>
</template>

<style lang="scss" scoped>
@import "./styles/generals.scss";
</style>
