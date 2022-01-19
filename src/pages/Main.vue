<template>
    <div class="wrapper">
        <Toolbar/>

        <div class="content">
            <Card 
                v-for="(card, index) of cards"
                :key="index"
                :card="card"
            >
            </Card>
        </div>
    </div>
</template>

<script>
    import Toolbar from '@/components/Toolbar.vue'
    import Card from '@/components/Card.vue'

    export default {
        components: {
            Toolbar,
            Card
        },

        data: () => ({
            cards: [
                {
                    price: '7 733 300 руб.',
                    type: 'Квартира',
                    number: 'кв. 62',
                    roomCount: '1 комн. кв.',
                    square: '234.38 м²',
                    floorNumber: '7 этаж',
                    address: 'Лен. область, Всеволожский район,д. Кудрово, ул. Столичная, д. 5, к. 1',
                    street: 'Чистое Небо, корпус 10, III кв. 2022 г.',
                    dealType: 'Уступка от юр. лица',
                },
                {
                    price: '7 733 300 руб.',
                    type: 'Квартира',
                    number: 'кв. 62',
                    roomCount: '1 комн. кв.',
                    square: '234.38 м²',
                    floorNumber: '7 этаж',
                    address: 'Комендантский пр., уч. 1 Каменка',
                    street: 'Зеленый квартал на Пулковских высотах, корпус 10, III кв. 2022 г.',
                    dealType: 'Уступка от физ. лица'
                },
                {
                    price: '800 300 руб.',
                    type: 'Паркинг',
                    number: null,
                    roomCount: '№ 7-10-2 (ПИБ №68)',
                    square: '15 м²',
                    floorNumber: null,
                    address: 'Ленинградская область, Всеволожский район, д. Кудрово, ул. Столичная, д. 5, к. 1',
                    street: 'Зеленый квартал на Пулковских высотах, корпус 10, III кв. 2022 г.',
                    dealType: 'Забронировано'
                },
                {
                    price: '800 300 руб.',
                    type: 'Паркинг',
                    number: null,
                    roomCount: '№ 7-10-2 (ПИБ №68)',
                    square: '15 м²',
                    floorNumber: null,
                    address: 'Ленинградская область, Всеволожский район, д. Кудрово, ул. Столичная, д. 5, к. 1',
                    street: 'Зеленый квартал на Пулковских высотах, корпус 10, III кв. 2022 г.',
                    dealType: 'Продано'
                }
            ]
        })
        
    }
</script>

<style lang="scss" scoped>
    .wrapper {
        font-family: 'PT Sans', sans-serif;
        font-size: 14px;
        padding: 39px 100px;
        max-width: 1200px;
        width: 100%;
        margin: 0 auto;
        background:  #F7F6F4;
    }

    .content {
        margin-top: 20px;
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
    }
</style>