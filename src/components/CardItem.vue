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


</style>