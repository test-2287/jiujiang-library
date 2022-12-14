<script>
import ChartHeader from './ChartHeader.vue'
import { defineComponent } from 'vue';

import { Swiper, SwiperSlide } from 'swiper/vue'
import { Autoplay } from 'swiper'
import 'swiper/css';

export default defineComponent({
    name: 'BookBorrowList',
    components: { ChartHeader, Swiper, SwiperSlide },
    setup() {
        return { modules: [Autoplay]  }
    }
})
</script>

<template>
    <div class="sub-chart-container">
        <ChartHeader :title="'本月图书借阅排行榜'"/>
        <div class="borrow-list">
        <swiper 
            :direction="'vertical'" 
            :slidesPerView="5"
            :autoplay="{
                delay:3000
            }"
            :loop="true"
            :modules="modules">

        <SwiperSlide>
            <div class="list-item">
                <div class="item-left">
                    <div class="icon" style="background-image: url('/list-orange.png');">
                        <span :style="'background: linear-gradient(180deg, #FFFFFF 37.04%, #FF5823 100%);-webkit-background-clip: text;background-clip: text;'">1</span>
                    </div>
                    <span class="book-name">存在主义咖啡馆 : 自由、存在和杏子鸡尾酒</span>
                </div>
                <div class="item-right">
                    <span>借阅</span>
                    <span>99</span>
                </div>
            </div>
        </SwiperSlide>

        <SwiperSlide>
            <div class="list-item">
                <div class="item-left">
                    <div class="icon" style="background-image:url('/list-orange.png')">
                        <span :style="'background: linear-gradient(180deg, #FFFFFF 37.04%, #FF5823 100%);-webkit-background-clip: text;background-clip: text;'">2</span>
                    </div>
                    <span class="book-name">存在主义咖啡馆 : 自由、存在和杏子鸡尾酒</span>
                </div>
                <div class="item-right">
                    <span>借阅</span>
                    <span>99</span>
                </div>
            </div>
        </SwiperSlide>

        <SwiperSlide>
            <div class="list-item">
                <div class="item-left">
                    <div class="icon" style="background-image: url('/list-orange.png')">
                        <span :style="'background: linear-gradient(180deg, #FFFFFF 37.04%, #FF5823 100%);-webkit-background-clip: text;background-clip: text;'">3</span>
                    </div>
                    <span class="book-name">存在主义咖啡馆 : 自由、存在和杏子鸡尾酒</span>
                </div>
                <div class="item-right">
                    <span>借阅</span>
                    <span>99</span>
                </div>
            </div>
        </SwiperSlide>

        <SwiperSlide>
            <div class="list-item">
                <div class="item-left">
                    <div class="icon">
                        <span>4</span>
                    </div>
                    <span class="book-name">存在主义咖啡馆 : 自由、存在和杏子鸡尾酒</span>
                </div>
                <div class="item-right">
                    <span>借阅</span>
                    <span>99</span>
                </div>
            </div>
        </SwiperSlide>

        <SwiperSlide>
            <div class="list-item">
                <div class="item-left">
                    <div class="icon">
                        <span>5</span>
                    </div>
                    <span class="book-name">存在主义咖啡馆 : 自由、存在和杏子鸡尾酒</span>
                </div>
                <div class="item-right">
                    <span>借阅</span>
                    <span>99</span>
                </div>
            </div>
        </SwiperSlide>

        <SwiperSlide>
            <div class="list-item">
                <div class="item-left">
                    <div class="icon">
                        <span>6</span>
                    </div>
                    <span class="book-name">存在主义咖啡馆 : 自由、存在和杏子鸡尾酒</span>
                </div>
                <div class="item-right">
                    <span>借阅</span>
                    <span>99</span>
                </div>
            </div>
        </SwiperSlide>

        <SwiperSlide>
            <div class="list-item">
                <div class="item-left">
                    <div class="icon">
                        <span>7</span>
                    </div>
                    <span class="book-name">存在主义咖啡馆 : 自由、存在和杏子鸡尾酒</span>
                </div>
                <div class="item-right">
                    <span>借阅</span>
                    <span>99</span>
                </div>
            </div>
        </SwiperSlide>

        <SwiperSlide>
            <div class="list-item">
                <div class="item-left">
                    <div class="icon">
                        <span>8</span>
                    </div>
                    <span class="book-name">存在主义咖啡馆 : 自由、存在和杏子鸡尾酒</span>
                </div>
                <div class="item-right">
                    <span>借阅</span>
                    <span>99</span>
                </div>
            </div>
        </SwiperSlide>

        <SwiperSlide>
            <div class="list-item">
                <div class="item-left">
                    <div class="icon">
                        <span>9</span>
                    </div>
                    <span class="book-name">存在主义咖啡馆 : 自由、存在和杏子鸡尾酒</span>
                </div>
                <div class="item-right">
                    <span>借阅</span>
                    <span>99</span>
                </div>
            </div>
        </SwiperSlide>

        <SwiperSlide>
            <div class="list-item">
                <div class="item-left">
                    <div class="icon">
                        <span>10</span>
                    </div>
                    <span class="book-name">存在主义咖啡馆 : 自由、存在和杏子鸡尾酒</span>
                </div>
                <div class="item-right">
                    <span>借阅</span>
                    <span>99</span>
                </div>
            </div>
        </SwiperSlide>

        </swiper>
        </div>
    </div>
</template>

<style scoped lang="scss">
:deep(.swiper.swiper-vertical) {
    height: 250px;
}

.borrow-list {
    padding: 0 7px;
    padding-top: 5px;
    height: 250px;
    overflow: hidden;
    
    .list-item {
        box-sizing: border-box;
        height: 50px;
        padding: 5px 10px;
        display: flex;
        justify-content: space-between;   
        align-items: center;
        overflow: hidden;
        /* &:nth-child(-n+3) {
            .item-left .icon {
                background-image: url('/list-orange.png');
                > span {
                    background: linear-gradient(180deg, #FFFFFF 37.04%, #FF5823 100%);
                    -webkit-background-clip: text;
                    -webkit-text-fill-color: transparent;
                    background-clip: text;
                }
            }
        } */
    }

    .item-left {
        display: flex;
        align-items: center;
        .icon {
            display: flex;
            justify-content: center;
            margin-right: 14px;
            width: 36px;
            height: 25px;
            height: 41px;   
            background-size: contain;
            background-image: url('/list-blue.png');
            background-position: center bottom;
            background-repeat: no-repeat;
            > span {
                font-weight: 700;
                font-size: 25px;
                line-height: 33px;
                background: linear-gradient(180deg, #FFFFFF 11.11%, #4AB0F7 100%);
                -webkit-background-clip: text;
                -webkit-text-fill-color: transparent;
                background-clip: text;
            }
        }
        .book-name {
            max-width: 256px;   
            white-space: nowrap;
            text-overflow: ellipsis;
            overflow: hidden;
            font-size: 15px;
            line-height: 20px;
            color: #FFFFFF;
        }
    }
    .item-right {
        display: flex;
        align-items: center;
        > span:first-child {
            font-size: 12px;
            line-height: 16px;
            color: #62697D;
            margin-right: 10px;
        }
        > span:nth-child(2) {
            width: 30px;
            height: 26px;
            background-image: url('/icon-borrow.png');
            background-size: cover;
            color: #fff;
            font-size: 16px;
            line-height: 21px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-weight: 700;
        }
    } 
}
</style>