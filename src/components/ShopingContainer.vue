<template>
    <div class="shoping-panel">
        <shoping-card v-for="cards in shopingListArray" :key="cards.id" :shoping-card-data="cards" />
    </div>
</template>

<script>
import ShopingCard from './ShopingCard.vue'

export default {
    name: 'ShopingContainer',

    components: { ShopingCard },

    props: {
        shopingListArray: {
            type: Array,
            default: () => [],
        },
    },
}
</script>

<style lang="scss" scoped>
.shoping-panel {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 20px;
    margin: 50px auto;
    background: #333030;
    border-radius: 15px;
}
</style>
