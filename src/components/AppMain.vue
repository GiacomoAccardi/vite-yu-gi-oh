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
        //console.log(store.cardsList)
      });
    },
  },
}
</script>

<template>
    <main>
        <div class="container">
            <div class="content">

                <div
                  class="column-5"
                  v-for="card in store.cardsList"
                  :key="card.id">
                    <img
                      :src="card.card_images[0].image_url_small"
                      :alt="card.name">
                    <div class="infobox">
                        <h3>{{ card.name }}</h3>
                        <p>{{ card.archetype }}</p>
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
main {
    padding: 60px 0;

    .container {

        .content{
            display: flex;
            flex-direction: row;
            flex-wrap: wrap;
            background-color: white;
            padding: 60px;

            .column-5{
                width: calc(100% / 5);
                padding: 10px;

                img{
                    width: 100%;
                }

                .infobox{
                    color: white;
                    text-align: center;
                    background-color: #D48F38;
                    padding: 20px;
                    min-height: 150px;

                    p{
                        margin-top: 30px;
                        color: black;
                    }
                }
            }
        }
    }
}
</style>