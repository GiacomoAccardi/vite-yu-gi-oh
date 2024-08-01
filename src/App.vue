<script>
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'
import Select from './components/Select.vue';

export default {
  components: {
    AppHeader,
    AppMain,
    Select
  }
}
</script>

<template>
  <div>
    <AppHeader />
    <Select />
    <AppMain />
  </div>
</template>

<style lang="scss">
@import "./styles/generals.scss";
</style>
