<template>
    <div class="toolbar">
        <div class="toolbar__selects">
            <div class="toolbar__search rounded-0">
                <v-text-field
                    class="rounded-0"
                    label="Введите ЖК / корпус / № квартиры / № паркинга"
                    outlined
                    hide-details
                    prepend-inner-icon="mdi-magnify"
                    height=38px
                    dense
                >
                </v-text-field>
            </div>

            <div class="toolbar__select rounded-0">
                <v-select
                    :items="items"
                    class="rounded-0"
                    label="Все статусы"
                    color="white"
                    outlined
                    hide-details
                    dense
                    multiple
                >
                    <template v-slot:item="item">
                        <div>
                            <v-checkbox
                                color="#FCE66F"
                                :label="`${item.item}`"
                                hide-details
                                dense
                            >
                            </v-checkbox>
                        </div>
                    </template>
                </v-select>
            </div>
            
            <div class="toolbar__btn">
                <v-btn
                    color="#E5E5E5"
                    depressed
                    height="100%"
                    tile
                >
                    <span>Очистить корзину</span>
                    <v-icon color="black" class="mt-1 ml-1">mdi-close</v-icon> 
                </v-btn>
            </div>
        </div>

        <div class="toolbar__btns">
            <div class="toolbar__checkbox">
                <v-checkbox
                    color="#FCE66F"
                    label="все"
                    hide-details
                    dense
                    style="color: black"
                >
                </v-checkbox>
            </div>

            <div class="toolbar__btn">
                <v-btn
                    color="#E5E5E5"
                    depressed
                    height="100%"
                    tile
                >
                    <span>Сохранить</span>
                </v-btn>
            </div>

            <div class="toolbar__btn">
                <v-btn
                    color="#E5E5E5"
                    depressed
                    height="100%"
                    tile
                >
                    <span>Отправить</span>
                </v-btn>
            </div>

            <div class="toolbar__btn">
                <v-btn
                    color="#E5E5E5"
                    depressed
                    height="100%"
                    block
                    tile
                >
                    <span>Удалить</span>
                </v-btn>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data: () => ({
            items: ["Забронировано", "Продано", "Активно"]
        }),
        components: {
            
        }
    }
</script>

<style lang="scss">
    .toolbar {
        &__selects {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap
        }

        &__btns {
            margin-left: 24px;
            margin-top: 32px;
            display: flex;
            justify-content: space-between;
            max-width: 500px;
            width: 100%;
        }

        &__search {
            max-width: 637px;
            width: 100%;
            border-radius: 0px;
            height: 38px;
        }

        &__select {
            font-style: normal;
            font-weight: normal;
            font-size: 13px;
            line-height: 20px;
            color: #000000;
            text-decoration: none;
            max-width: 180px;
            width: 100%;
            height: 38px;
        }

        &__checkbox {
            display: flex;
            align-items: center;

            &:first-child {
                margin-top: 0;
            }
        }

        &__btn {
            font-size: 13px;
            display: flex;
            height: 40px;
            max-width: 154px;
            width: 100%;

            &:first-child {
                padding: 0;
                font-style: normal;
                font-weight: normal;
                font-size: 13px;
                line-height: 20px;
                color: #000;
            }

            &:not(:first-of-type) {
                max-width: 116px !important;
                width: 100%;
                padding: 0;
                font-style: normal;
                font-weight: normal;
                font-size: 13px;
                line-height: 20px;
            }
        }
    }

    .v-input--selection-controls {
        margin-top: 0 !important;
        padding-top: 0 !important;
    }

</style>