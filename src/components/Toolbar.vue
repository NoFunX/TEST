<template>
    <div class="toolbar">
        <div class="toolbar__selects">
            <div class="toolbar__search">
                <v-text-field
                    class="rounded-0"
                    placeholder="Введите ЖК / корпус / № квартиры / № паркинга"
                    outlined
                    hide-details
                    height=38px
                    dense
                >
                    <template v-slot:prepend-inner>
                        <img width="14" height="14" src="@/assets/search.svg" class="mt-1 mr-4">
                    </template>
                </v-text-field>
            </div>

            <div class="toolbar__select">
                <v-select
                    :items="items"
                    v-model="selected"
                    class="rounded-0 toolbar__select"
                    placeholder="Все статусы"
                    item-color="white"
                    append-icon="mdi-chevron-down"
                    height=38px
                    outlined
                    hide-details
                    dense
                    multiple
                    :menu-props="{offsetY: true, maxWidth: 180, bottom: true,}"
                >
                    <template v-slot:item="props">
                        <div>
                            <v-checkbox
                                color="#FCE66F"
                                hide-details
                                dense
                                :label="props.item"
                            >
                                <template v-slot:label>
                                    <span class="toolbar__select_item">{{ props.item }}</span>
                                </template>
                            </v-checkbox>
                        </div>
                    </template>

                   <template v-slot:selection="props"> 
                        <span :style="`line-height: 0 !important; ${selected.length > 1 ? 'margin-top: 8px' : null}`">
                            {{ props.item }}
                        </span>
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
                    <v-icon color="black" class="ml-2">mdi-close</v-icon> 
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
                    <img src="@/assets/pdf.svg" class="ml-3">
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
                    <img src="@/assets/airplane.svg" class="ml-3">
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
                    <img src="@/assets/delete.svg" class="ml-3">
                </v-btn>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data: () => ({
            items: ["Забронировано", "Продано", "Активно"],
            selected: []
        }),
        components: {
            
        }
    }
</script>

<style lang="scss">
    .toolbar {
        &__selects {
            display: flex;
            // justify-content: space-between;
            flex-wrap: wrap
        }

        &__btns {
            margin-left: 24px;
            margin-top: 32px;
            display: flex;
            justify-content: space-between;
            max-width: 450px;
            width: 100%;
        }

        &__search {
            max-width: 637px;
            width: 100%;
            border-radius: 0px;
            height: 38px;
            margin-right: 10px;
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
            margin-right: 10px;
            

            &_item {
                display: flex;
                color: black;
                font-size: 14px;
                line-height: 18px;
                color: #02101C;
                align-items: center;

                &:hover {
                    display: flex;
                    color: #FF0D29;
                }
            }

            &_selection {
                display: inline;
            }
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
                font-size: 13px !important;
                line-height: 20px !important;
            }
        }
    }

    .v-input--selection-controls {
        margin-top: 0 !important;
        padding-top: 0 !important;
    }
 
    .toolbar__select input::placeholder {
        font-size: 14px !important;
        line-height: 18px !important;
        color: #000000 !important;
        font-style: normal !important;;
        font-weight: normal !important;;
    }

</style>