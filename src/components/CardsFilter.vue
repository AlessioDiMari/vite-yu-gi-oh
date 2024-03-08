<script>
import { store } from '../store';

export default{
    name: 'CardsFilter',

    data(){
        return{
            store,
        }
    },
}

</script>



<template>

<select name="" id="card-filter">
    
    <option value="archetype">ciao</option>
    
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