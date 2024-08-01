
<script>
import { store } from '../store';
import axios from 'axios';

export default {
    data(){
        return {
            store
        }
    },
    created(){
        this.getArchetypes();
    },
    methods: {
    //creo una funzione per popolare l'array che conterrà le carte all'interno di store.js
    getArchetypes() {
      axios.get(store.apiArch).then((data) => {
        store.archList = data.data;
        console.log(store.archList)
      });
    },
  },
}
</script>

<template>
    <div class="container">
        <div class="content">
            <select name="tipe-select" id="ts">
                <option value="" disabled selected>- Seleziona un archetipo</option>
                <option value="" v-for="archetype in store.archList" :key="index">{{ archetype.archetype_name }}</option>
            </select>
        </div>
    </div>
</template>

<style lang="scss">
    .container{
        background-color: white;
        .content{
            padding: 20px;

            select{
                height: 50px;
                width: 270px;
                font-size: 14pt;
                padding: 0 20px;
            }

        }
    }
</style>