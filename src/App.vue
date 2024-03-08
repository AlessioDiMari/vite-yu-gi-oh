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

    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=30&offset=0')
      .then(res =>{
        console.log(res.data.data)
        this.store.cards = res.data.data;
      });

    // call API per la popolazione del select
    axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
      .then(res =>{
        console.log('archetipi', res.data)
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
