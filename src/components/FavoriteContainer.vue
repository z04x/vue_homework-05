<template>
    <div class="cards-penel">
        <favorite-card v-for="cards in cardListArray" :key="cards.id" :favorite-card-data="cards" />
    </div>
</template>

<script>
import FavoriteCard from './FavoriteCard.vue'
export default {
    name: 'FavoriteContainer',

    components: {
        FavoriteCard,
    },

    props: {
        cardListArray: {
            type: Array,
            default: () => [],
        },
    },
}
</script>

<style lang="scss" scoped>
.cards-penel {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 500px;
    height: 200px;
    margin: 50px auto;
    background: #241d1d;
    border-radius: 15px;
}
</style>
