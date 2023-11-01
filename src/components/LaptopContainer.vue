<template>
    <div class="laptop-panel">
        <laptop-card v-for="cards in laptopListArray" :key="cards.id" :laptop-card-data="cards" />
    </div>
</template>

<script>
import LaptopCard from '@/components/LaptopCard.vue'
export default {
    name: 'LaptopContainer',
    components: {
        LaptopCard,
    },
    props: {
        laptopListArray: {
            type: Array,
            default: () => [],
        },
    },
}
</script>

<style lang="scss" scoped></style>
