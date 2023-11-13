<template>
  <div v-if="loadingPg">
    <LoadingScreenComponent/>
  </div>
  <div v-else>
    <HeaderComponent/>
    <MainComponent/>
  </div>
</template>

<script>
  import {store} from './assets/data/store.js';
  import axios from 'axios';
  import HeaderComponent from './components/HeaderComponent.vue';
  import MainComponent from './components/MainComponent.vue';
  import LoadingScreenComponent from './components/LoadingScreenComponent.vue';
  export default {
    name: 'App',
    components: {
      HeaderComponent,
      MainComponent,
      LoadingScreenComponent
    },
    data() {
      return {
        store,
        loadingPg: true
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
      },
      LoadingPlay() {
        setTimeout(() => {
          this.loadingPg = false;
        },5000);
      }
    },
    created() {
      this.getCardsinfo();
    },
    mounted() {
      this.LoadingPlay();
    }
  }
</script>

<style lang="scss" scoped>
</style>
