<script>
import { store } from '../store.js';
import axios from 'axios';

export default {
    data() {
    return{
        store
    }
  },
  created() {
    this.getCards();
  },
  methods: {
    //creo una funzione per popolare l'array che conterrà le carte all'interno di store.js
    getCards() {
      axios.get(store.apiUrl).then((response) => {
        store.cardsList = response.data.data;
        console.log(store.cardsList)
      });
    },
  },
}
</script>

<template>
    <main>
        <div class="container">
            <div class="content">
                <div class="column-5" v-for="card in store.cardsList" :key="card.id">
                    {{ card.name }}
                </div>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
main {
    padding: 60px 0;

    .container {
        max-width: 1200px;
        margin: 0 auto;
        display: flex;
        justify-content: center;
        align-items: center;

        .content{
            display: flex;
            flex-direction: row;
            flex-wrap: wrap;
            background-color: white;

            .column-5{
                width: calc(100% / 5);
            }
        }
    }
}
</style>