<script>
import {store} from '../store.js';
import CardItem from './CardItem.vue';
import CardsFilter from './CardsFilter.vue';
import axios from 'axios';

export default{
    name: 'AppCardsList',

    data(){
        return{
            store,
        }
    },
    components:{
        CardItem,
        CardsFilter,
    },

    methods: {
        filterCards(){
            // chiamata API a seconda dell'archetipo
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=30&offset=0&archetype=' + this.store.archetypeValue )
            .then(res =>{
                this.store.cards = res.data.data;
            });
        }
    }

}

</script>


<template>

<div class="container">
    <h2>Lista Carte</h2>

    <CardsFilter @filter="filterCards"></CardsFilter>
    
    <ul>
        <CardItem v-for="actualCard in store.cards" :card="actualCard"></CardItem>
    </ul>

</div>

</template>


<style lang="scss">

.container{

    padding: 24px;

    h2{
        text-align: center;
        margin-bottom: 24px;
    }

    ul{
        display: flex;
        flex-wrap: wrap;
        gap: 20px;
    }
}


</style>