<script>
import ChartHeader from './ChartHeader.vue'
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'BookBorrowList',
    components: { ChartHeader },
    setup() {
        return {  }
    }
})
</script>

<template>
    <div class="sub-chart-container">
        <ChartHeader :title="'本月图书借阅排行榜'"/>
        <div class="borrow-list">
            <div class="list-item">
                <div class="item-left">
                    <div class="icon">
                        <span>1</span>
                    </div>
                    <span class="book-name">存在主义咖啡馆 : 自由、存在和杏子鸡尾酒</span>
                </div>
                <div class="item-right">
                    <span>借阅</span>
                    <span>99</span>
                </div>
            </div>
            <div class="list-item">
                <div class="item-left">
                    <div class="icon">
                        <span>2</span>
                    </div>
                    <span class="book-name">存在主义咖啡馆 : 自由、存在和杏子鸡尾酒</span>
                </div>
                <div class="item-right">
                    <span>借阅</span>
                    <span>99</span>
                </div>
            </div>
            <div class="list-item">
                <div class="item-left">
                    <div class="icon">
                        <span>3</span>
                    </div>
                    <span class="book-name">存在主义咖啡馆 : 自由、存在和杏子鸡尾酒</span>
                </div>
                <div class="item-right">
                    <span>借阅</span>
                    <span>99</span>
                </div>
            </div>
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

        </div>
    </div>
</template>

<style scoped lang="scss">
.borrow-list {
    padding: 0 7px;
    padding-top: 5px;
    
    .list-item {
        height: 50x;
        padding: 5px 10px;
        display: flex;
        justify-content: space-between;   
        align-items: center;
        &:nth-child(-n+3) {
            .item-left .icon {
                background-image: url('/list-orange.png');
                > span {
                    background: linear-gradient(180deg, #FFFFFF 37.04%, #FF5823 100%);
                    -webkit-background-clip: text;
                    -webkit-text-fill-color: transparent;
                    background-clip: text;
                }
            }
        }
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