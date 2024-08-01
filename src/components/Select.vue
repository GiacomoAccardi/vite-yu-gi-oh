
<script>
import { store } from '../store';
export default {
    data(){
        return {
            store
        }
    }
}
</script>

<template>
    <div class="container">
        <div class="content">
            <select name="tipe-select" id="ts">
                <option value="" disabled selected>- Seleziona un archetipo</option>
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