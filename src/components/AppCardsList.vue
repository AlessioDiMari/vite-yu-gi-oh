<script>
import {store} from '../store.js';
import CardItem from './CardItem.vue';

export default{
    name: 'AppCardsList',

    data(){
        return{
            store,
        }
    },
    components:{
        CardItem,
    }

}

</script>


<template>

<div class="container">
    <h2>Lista Carte</h2>

    <ul>
        <CardItem v-for="actualCard in store.cards" :card="actualCard"></CardItem>
    </ul>

</div>

</template>


<style lang="scss">




</style>