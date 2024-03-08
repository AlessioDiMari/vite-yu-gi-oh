<script>
import {store} from '../store.js';
import CardItem from './CardItem.vue';
import CardsFilter from './CardsFilter.vue';

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
    }

}

</script>


<template>

<div class="container">
    <h2>Lista Carte</h2>

    <CardsFilter></CardsFilter>
    
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