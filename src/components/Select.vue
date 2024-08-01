
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
        //con la riga di codice sottostante recupero dall'api solo gli archetipi che mi interessano
        store.archList = data.data.filter((data, index) => [15, 251, 350, 318, 32].includes(index));
        //console.log(store.archList)
      });
    },
  },
}
</script>

<template>
    <div class="container">
        <div class="content">
            <h4>Cerca carte per archetipo</h4>
            <select name="tipe-select" id="ts">
                <option value="" disabled selected>- Seleziona un archetipo</option>
                <option
                  :value="archetype.archetype_name"
                  v-for="archetype in store.archList"
                  :key="index">{{ archetype.archetype_name }}</option>
            </select>
        </div>
    </div>
</template>

<style lang="scss">
    .container{
        background-color: white;
        .content{
            padding: 20px;

            h4{
                margin-bottom: 10px;
            }

            select{
                height: 50px;
                width: 270px;
                font-size: 14pt;
                padding: 0 20px;
            }

        }
    }
</style>