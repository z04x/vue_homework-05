<template>
    <p class="task-description">Задача 1.(проверял работу)</p>
    <favorite-container :card-list-array="favoriteSources" />
    <p class="task-description">Задача 2</p>
    <shoping-container :shoping-list-array="shoppingSources" />
    <p class="task-description">Задача 3</p>
    <laptop-container :laptop-list-array="laptopInfo" />
</template>

<script>
//* import components */
import FavoriteContainer from '@/components/FavoriteContainer.vue'
import ShopingContainer from '@/components/ShopingContainer.vue'
import LaptopContainer from './components/LaptopContainer.vue'
//* import Data for cards */
import { favoriteSources } from '@/constants/1_data_google_favorite'
import { shoppingSources } from '@/constants/2_data_google_shopping_search'
import { laptopInfo } from '@/constants/3_data_laptop_info'

export default {
    name: 'App',
    components: {
        FavoriteContainer,
        ShopingContainer,
        LaptopContainer,
    },
    data() {
        return {
            favoriteSources,
            shoppingSources,
            laptopInfo,
        }
    },
}
</script>

<style lang="scss">
@import './assets/style';
</style>
