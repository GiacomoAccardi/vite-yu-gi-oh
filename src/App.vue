<script>
import { store } from './store.js' //importo il file store.js
import axios from 'axios';
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'

export default {
  data() {
    store
  },
  components: {
    AppHeader,
    AppMain
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
    <AppHeader />
    <AppMain />
  </div>
</template>

<style lang="scss">
@import "./styles/generals.scss";
</style>
