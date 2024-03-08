<script>
import axios from 'axios';
import { store } from './store';
import AppCardsList from './components/AppCardsList.vue';

export default{
  data(){
    return{

      store,

    }
  },

  components:{
    AppCardsList,
  },

  created(){
    // chiamata all'API per popolare home page con le carte
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=30&offset=0')
      .then(res =>{
        this.store.cards = res.data.data;
      });

    // call API per la popolazione del select
    axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
      .then(res =>{
        this.store.archetypes = res.data
      })

  }

}

</script>

<template>

<AppCardsList></AppCardsList>

</template>

<style lang="scss">

</style>
