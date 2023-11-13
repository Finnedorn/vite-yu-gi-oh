<template>
  <HeaderComponent/>
  <MainComponent/>
</template>

<script>
  import {store} from './assets/data/store';
  import axios from 'axios';
  import HeaderComponent from './components/HeaderComponent.vue';
  import MainComponent from './components/MainComponent.vue';
  export default {
    name: 'App',
    components: {
      HeaderComponent,
      MainComponent
    },
    data() {
      return {
        store
      }
    }
  }
</script>

<style lang="scss" scoped>

</style>
