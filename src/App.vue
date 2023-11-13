<template>
  <HeaderComponent/>
  <MainComponent/>
</template>

<script>
  import {store} from './assets/data/store.js';
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
    },
    methods: {
      getCardsinfo() {
        const url = this.store.apiUrl
        axios.get(url).then((response) => {
          console.log(response.data.data);
          store.cardList = response.data.data;
          console.log(store.cardList);
        })
      }
    },
    created() {
      this.getCardsinfo();
    }
  }
</script>

<style lang="scss" scoped>

</style>
