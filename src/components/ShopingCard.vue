<template>
    <div class="shoping-card__container">
        <div class="shoping-card__content">
            <div class="shoping-card__image">
                <a :href="shopingCardData.link">
                    <img :src="shopingCardData.imgSrc" />
                </a>
            </div>
            <div :class="{ availability: shopingCardData.itemAvailability }" class="shoping-card__title">
                <a :href="shopingCardData.link">
                    {{ shopingCardData.shopName }}
                </a>
            </div>
            <p class="shoping-card__text">{{ shopingCardData.text }}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ShopingCard',
    props: {
        shopingCardData: {
            type: Object,
            default: () => ({}),
        },
    },
}
</script>

<style lang="scss" scoped>
.shoping-card {
    &__container {
        color: aliceblue;
    }

    &__content {
        width: 212px;
        padding: 8px;
        overflow: hidden;
        text-overflow: ellipsis;
        background: #333030;
        border: 1px rgba(85, 77, 77, 0.966) solid;
        border-radius: 15px;
        margin-right: 40px;
    }

    &__image {
        img {
            width: 212px;
            height: 212px;
            object-fit: cover;
            border-radius: 15px;
        }
    }

    &__title {
        &.availability {
            &::after {
                content: ' - В наличии';
                color: rgb(26, 219, 26);
            }
        }
    }

    &__text {
        width: 212px; /* Укажите желаемую ширину блока */
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
    }
}
</style>
