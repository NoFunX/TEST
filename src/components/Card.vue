<template>
    <div class="card">
        <v-card 
            height="100%" 
            hover 
            tile
        >
            <div class="content">
                .
                <span class="price">{{ card.price }}</span>

                <div class="type">
                    <img
                        v-if="card.type === 'Квартира'" 
                        src="@/assets/flat.svg" 
                        class="mr-2"
                    >

                    <img
                        v-if="card.type === 'Паркинг'" 
                        src="@/assets/car.svg" 
                        class="mr-2"
                    >
                    <span> {{ card.type }} </span>
                </div>

                <div
                    v-if="card.dealType === 'Уступка от юр. лица'" 
                    class="dealType"
                >
                    <div class="dealType__circle"></div>
                    <span class="dealType__text">{{ card.dealType }}</span>
                </div>

                <div
                    v-if="card.dealType === 'Уступка от физ. лица'" 
                    class="dealType--physical"
                >
                    <div class="dealType--physical__circle"></div>
                    <span class="dealType--physical__text">{{ card.dealType }}</span>
                </div>

                <div
                    v-if="card.dealType === 'Забронировано'" 
                    class="dealType--booked"
                >
                    <div class="dealType--booked__circle"></div>
                    <span class="dealType--booked__text">{{ card.dealType }}</span>
                </div>

                <div
                    v-if="card.dealType === 'Продано'" 
                    class="dealType--sold"
                >
                    <div class="dealType--sold__circle"></div>
                    <span class="dealType--sold__text">{{ card.dealType }}</span>
                </div>

                <div class="street">
                    {{ card.street.split(',')[0] + ', ' }} 
                    <span class="street--desc"> {{ card.street.split(',')[1] + ', ' +  card.street.split(',')[2] }} </span>
                </div>

                <v-checkbox
                    class="checkbox"
                    color="#FCE66F"
                    hide-details
                    dense
                >
                </v-checkbox>

                <div class="params">
                    <div class="room-params">
                        <div 
                            v-if="card.number"
                            class="room-params__number"
                        >
                            {{ card.number }}
                        </div>
                        <div class="room-params__count">{{ card.roomCount }}</div>
                    </div>

                    <hr v-if="card.number" class="divider">
                    <hr v-if="!card.number" class="divider-parking">

                    <div class="room-params">
                        <div class="room-params__number">{{ card.square }}</div>
                        <div 
                            v-if="card.floorNumber"
                            class="room-params__count"
                        >
                            {{ card.floorNumber }}
                        </div>
                    </div>
                    
                </div>

                <div class="address">
                    <img src="@/assets/geo.svg" class="mr-2">
                    <span> {{ card.address }} </span>
                </div>

                <img src="@/assets/plan.svg" class="plan">
            </div>
        </v-card>
    </div>
</template>

<script>
export default {
    props: {
        card: {
            type: Object,
            default: () => {}
        }
    }
}
</script>

<style lang="scss" scoped>
    .card {
        width: 489px;
        position: relative;

        &:nth-child(3) {
            margin-top: 23px;
        }
        &:nth-child(4) {
            margin-top: 23px;
        }

        .content {
            margin: 25px 0 25px 25px;
            display: inline-block;
        }
    }

    .price {
        margin-left: 25px;
        font-size: 15px;
        line-height: 20px;
        color: #FF0D29;
        font-weight: bold;
    }

     .type {
        display: inline-flex;
        margin-left: 16px;
        box-shadow: 0px 0px 2px rgba(94, 119, 157, 0.25);
        border-radius: 32px;
        font-size: 12px;
        line-height: 16px;
        color: #232735;
        padding: 5px 16px
    }

    .dealType {
        display: inline-flex;
        align-items: center;
        justify-content: center;
        background: #FFE4E4;
        padding: 6px 9px;
        position: absolute;
        right: 0;
        top: 21px;

        &__circle {
            width: 6px;
            height: 6px;
            border-radius: 50%;
            background: #DD4C5D;
            margin-right: 8px;
        }

        &__text {
            font-size: 14px;
            line-height: 18px;
            color: #DD4C5D;
        }

        &--physical {
            background: #D6F5FF;
            padding: 6px 9px;
            position: absolute;
            right: 0;
            top: 21px;
            display: inline-flex;
            align-items: center;
            justify-content: center;

            &__circle {
                width: 6px;
                height: 6px;
                border-radius: 50%;
                background: #0291C1;
                margin-right: 8px;
            }

            &__text {
                font-size: 14px;
                line-height: 18px;
                color: #0291C1;
            }
        }

        &--booked {
            background: #EDEDED;
            padding: 6px 9px;
            position: absolute;
            right: 0;
            top: 21px;
            display: inline-flex;
            align-items: center;
            justify-content: center;

            &__circle {
                width: 6px;
                height: 6px;
                border-radius: 50%;
                background:#686868;
                margin-right: 8px;
            }

            &__text {
                font-size: 14px;
                line-height: 18px;
                color:#686868;
            }
        }

        &--sold {
            background: #CCCCCC;
            padding: 6px 9px;
            position: absolute;
            right: 0;
            top: 21px;
            display: inline-flex;
            align-items: center;
            justify-content: center;

        &__circle {
            width: 6px;
            height: 6px;
            border-radius: 50%;
            background:#808080;
            margin-right: 8px;
        }

        &__text {
            font-size: 14px;
            line-height: 18px;
            color:#808080;
        }
        }
    }

    .street {
        margin-left: 30px;
        margin-top: 6px;
        font-size: 14px;
        line-height: 150%;
        color: #000000;
        width: 230px;

        &--desc {
            color: grey
        }
    }

    .checkbox {
        margin-top: 39px !important;
        display: inline-block;
        margin-right: 1px;
    }

    .params {
        margin-top: 35px;
        display: inline-flex;
        padding-top: 10px;

        .room-params__number, .room-params__count {
            font-size: 14px;
            line-height: 25px;
            color: #000000;
        }
    }

    .divider {
        width: 48px;
        transform: rotate(90deg);
        margin-top: 25px;
    }

    .divider-parking {
        width: 25px;
        transform: rotate(90deg);
        margin-top: 15px;
    }

    .address {
        margin-top: 19px;
        margin-left: 20px;
        font-size: 14px;
        line-height: 150%;
        color: #000000;
        display: flex;
        width: 270px;
    }

    .plan {
        position: absolute;
        top: 78px;
        left: 331px;
    }
</style>