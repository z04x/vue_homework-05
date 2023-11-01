<template>
    <div class="laptop-card__container">
        <div class="laptop-card__content">
            <div class="laptop-card__image">
                <a :href="laptopCardData.link">
                    <img :src="laptopCardData.imgSrc" />
                </a>
            </div>
            <div class="laptop-card__info-content">
                <h5 class="laptop-card__model">{{ laptopCardData.title }}</h5>
                <div class="laptop-card__price">
                    <span>{{ laptopCardData.price }}₴</span>
                </div>
                <!-- Проверяем наличие скидки и отображаем информацию о скидке, если есть -->
                <div v-if="laptopCardData.discountPrice">
                    <p class="laptop-card__discounted-price">
                        <span>{{ laptopCardData.discountPrice }}₴</span>
                    </p>
                    <p class="laptop-card__cost-saving">Сэкономлено: {{ discountedSavings }}₴</p>
                </div>
                <a :href="laptopCardData.link" class="laptop-card__button">Купить</a>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'LaptopCard',
    props: {
        laptopCardData: {
            type: Object,
            default: () => ({}),
        },
    },
    data() {
        return {
            // Локальная переменная для сэкономленной суммы
            discountedSavings: null,
        }
    },
    created() {
        // Проверяем наличие скидки и вычисляем сэкономленную сумму
        if (this.laptopCardData.discountPrice) {
            this.discountedSavings = this.laptopCardData.price - this.laptopCardData.discountPrice
        }
    },
}
</script>

<style lang="scss" scoped>
.laptop-card {
    &__container {
        padding-top: 50px;
    }

    &__content {
        display: flex;
        gap: 50px;
        border-radius: 15px;
        border: 2px solid #6e6e6e6e;
        padding: 10px;
        margin-bottom: 15px;
    }
    &__info-content {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
    }
    &__image {
        width: 212px;
        height: 212px;
        background: #6e6e6e28;
        padding: 15px;
        border-radius: 15px;
        img {
            object-fit: contain;
            width: 100%;
            height: 100%;
        }
    }

    &__model {
    }

    &__price {
        span {
            font-size: 24px;
            font-weight: 600;
            color: rgb(214, 68, 68);
        }
    }

    &__discounted-price {
        span {
            font-size: 14px;
            font-weight: 600;
            color: rgba(87, 86, 86, 0.541);
            text-decoration: line-through red;
        }
    }

    &__cost-saving {
        text-decoration: underline;
    }

    &__button {
        background: green;
        max-width: 100px;
        padding: 11px 25px;
        border-radius: 5px;
        color: aliceblue;
    }
}
</style>
