<template>
    <div class="card__container">
        <div class="card__content">
            <div class="card__image">
                <img :src=" favoriteCardData.imgSrc" />
            </div>
            <div class="card__title">
                <a :href="favoriteCardData.link">{{  favoriteCardData.title }}</a>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'FavoriteCard',
    props: {
        // imgSrc: {
        //     type: String,
        //     default: '',
        // },
        // link: {
        //     type: String,
        //     default: '',
        // },
        // title: {
        //     type: String,
        //     default: '',
        // },
        favoriteCardData: {
            type: Object,
            default: () => ({}),
        },
    },
}
</script>

<style lang="scss" scoped>
.card {
    &__container {
        margin: 15px;
        display: flex;
        justify-content: center;
    }
    &__content {
        display: inline-block;
        background: #302727;
        border-radius: 15px;
        padding: 10px;
    }

    &__image {
        // width: 42px;
        // height: 42px;
        padding: 10px;
        background: #3d3232;
        border-radius: 50%;
        display: flex;
        justify-content: center;
        img {
            width: 32px;
            height: 32px;
            object-fit: cover;
        }
    }

    &__title {
        text-align: center;
        padding-top: 10px;
        font-size: 16px;
        color: #ffffff;
    }
}
</style>
