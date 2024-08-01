
<script>
export default {
    
}
</script>

<template>
    <div class="container">
        <div class="content">
            <select name="tipe-select" id="ts">
                <option value="null">Seleziona un archetipo</option>
            </select>
        </div>
    </div>
</template>

<style lang="scss">
    .container{
        background-color: white;
        .content{
            padding: 40px;

            select{
                height: 50px;
                width: 250px;
                font-size: 14pt;
            }

        }
    }
</style>