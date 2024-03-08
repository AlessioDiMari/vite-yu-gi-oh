<script>
import { store } from '../store';

export default{
    name: 'CardsFilter',

    data(){
        return{
            store,
        }
    },

    methods(){

    },

}

</script>



<template>

<select name="card-filter" id="card-filter" @change="$emit('filter')" v-model="store.archetypeValue">

    <option v-for="actualArchetype in store.archetypes" :value="actualArchetype.archetype_name">{{ actualArchetype.archetype_name }}</option>
    
</select>

</template>



<style lang="scss">

select{
    margin: 24px;
    padding: 8px 12px;
    width: calc(100% / 8);
    border-radius: 0.5em;
}

</style>