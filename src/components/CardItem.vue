<script>
export default{
    name: 'CardItem',

    data(){
        return{

        }
    },

    props: {
        card: Object,
    }
}

</script>

<template>

    <li class="card">
        <img :src="card.card_images[0].image_url" :alt="card.name">
        <strong>{{ card.name }}</strong>
        <span>{{ card.archetype }}</span>
    </li>

</template>

<style lang="scss">

.card{
    display: flex;
    flex-direction: column;
    gap: 12px;
    width: calc(100% / 5 - 20px / 5 * 4);
    text-align: center;
    background-color: rgb(0, 118, 236);
    border-radius: 5px;
    overflow: hidden;
    
    span{
        color: black;
    }

}

</style>