<template>
  <div v-if="loadingPg">
    <LoadingScreenComponent/>
  </div>
  <div v-else>
    <HeaderComponent/>
    <SelectComponent @filter-select="setParams"/>
    <MainComponent/>
  </div>
</template>

<script>
  import {store} from './assets/data/store.js';
  import axios from 'axios';
  import HeaderComponent from './components/HeaderComponent.vue';
  import MainComponent from './components/MainComponent.vue';
  import LoadingScreenComponent from './components/LoadingScreenComponent.vue';
  import SelectComponent from './components/SelectComponent.vue';
  export default {
    name: 'App',
    components: {
      HeaderComponent,
      MainComponent,
      LoadingScreenComponent,
      SelectComponent
    },
    data() {
      return {
        store,
        loadingPg: true,
        activeParams: {
          num: 20,
          offset: 0
        }
      }
    },
    methods: {
      //select è un valore fantoccio, non specificandolo nell @filter-select automaticamente è implicito il valore che ho importato con $emit
      setParams(select) {
        console.log(select)
        //activeparams diventa un oggeto con key archetypo a seconda del valore del select cioè activeselect
        this.activeParams = {
          num: 20,
          offset:0,
          archetype: select
        }
        this.getCardsinfo()
      },
      getCardsinfo() {
        const url = this.store.apiUrl
        axios.get(url, {params: this.activeParams}).then((response) => {
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
