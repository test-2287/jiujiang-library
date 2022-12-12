<script>
import { defineComponent, onMounted, ref } from 'vue'
import ChartHeader from '../components/ChartHeader.vue'

import { Swiper, SwiperSlide } from 'swiper/vue'
import { Pagination, Autoplay } from 'swiper'
import 'swiper/css';

export default defineComponent({
    name: 'JicengBorrow',
    components: { ChartHeader, Swiper, SwiperSlide },
    setup() {
        return {
            modules: [Pagination, Autoplay]
        }
    }
})

</script>

<template>
    <div class="sub-chart-container">
        <ChartHeader :title="'今日基层服务点借阅统计'"/>
        <swiper :modules="modules" 
                :autoplay="{
                    delay: 3000
                }"
                :pagination="{
                    clickable: true
                }"
        >
            <SwiperSlide>
        <div class="jiceng-list">
            <div class="jiceng-item">
                <div class="jiceng-name">工人文化宫</div>
                <div class="data-item">
                    <span>借阅</span>
                    <span>36</span>        
                </div>
                <div class="data-item">
                    <span>还书</span>
                    <span>125</span>
                </div>
            </div>
            <div class="jiceng-item">
                <div class="jiceng-name">工人文化宫</div>
                <div class="data-item">
                    <span>借阅</span>
                    <span>36</span>        
                </div>
                <div class="data-item">
                    <span>还书</span>
                    <span>125</span>
                </div>
            </div>
            <div class="jiceng-item">
                <div class="jiceng-name">工人文化宫</div>
                <div class="data-item">
                    <span>借阅</span>
                    <span>36</span>        
                </div>
                <div class="data-item">
                    <span>还书</span>
                    <span>125</span>
                </div>
            </div>
            <div class="jiceng-item">
                <div class="jiceng-name">工人文化宫</div>
                <div class="data-item">
                    <span>借阅</span>
                    <span>36</span>        
                </div>
                <div class="data-item">
                    <span>还书</span>
                    <span>125</span>
                </div>
            </div>
        </div>
    </SwiperSlide> 

    <SwiperSlide>
        <div class="jiceng-list">
            <div class="jiceng-item">
                <div class="jiceng-name">工人文化宫</div>
                <div class="data-item">
                    <span>借阅</span>
                    <span>36</span>        
                </div>
                <div class="data-item">
                    <span>还书</span>
                    <span>125</span>
                </div>
            </div>
            <div class="jiceng-item">
                <div class="jiceng-name">工人文化宫</div>
                <div class="data-item">
                    <span>借阅</span>
                    <span>36</span>        
                </div>
                <div class="data-item">
                    <span>还书</span>
                    <span>125</span>
                </div>
            </div>
            <div class="jiceng-item">
                <div class="jiceng-name">工人文化宫</div>
                <div class="data-item">
                    <span>借阅</span>
                    <span>36</span>        
                </div>
                <div class="data-item">
                    <span>还书</span>
                    <span>125</span>
                </div>
            </div>
            <div class="jiceng-item">
                <div class="jiceng-name">工人文化宫</div>
                <div class="data-item">
                    <span>借阅</span>
                    <span>36</span>        
                </div>
                <div class="data-item">
                    <span>还书</span>
                    <span>125</span>
                </div>
            </div>
        </div>
    </SwiperSlide> 

    <SwiperSlide>
        <div class="jiceng-list">
            <div class="jiceng-item">
                <div class="jiceng-name">工人文化宫</div>
                <div class="data-item">
                    <span>借阅</span>
                    <span>36</span>        
                </div>
                <div class="data-item">
                    <span>还书</span>
                    <span>125</span>
                </div>
            </div>
            <div class="jiceng-item">
                <div class="jiceng-name">工人文化宫</div>
                <div class="data-item">
                    <span>借阅</span>
                    <span>36</span>        
                </div>
                <div class="data-item">
                    <span>还书</span>
                    <span>125</span>
                </div>
            </div>
            <div class="jiceng-item">
                <div class="jiceng-name">工人文化宫</div>
                <div class="data-item">
                    <span>借阅</span>
                    <span>36</span>        
                </div>
                <div class="data-item">
                    <span>还书</span>
                    <span>125</span>
                </div>
            </div>
            <div class="jiceng-item">
                <div class="jiceng-name">工人文化宫</div>
                <div class="data-item">
                    <span>借阅</span>
                    <span>36</span>        
                </div>
                <div class="data-item">
                    <span>还书</span>
                    <span>125</span>
                </div>
            </div>
        </div>
    </SwiperSlide> 

    
    </swiper>
    </div>
</template>

<style scoped lang="scss">
:deep(.swiper-pagination) {
    display: flex;
    justify-content: center;
    height: 10px;
}

:deep(.swiper-pagination-bullet) {
    margin-right: 10px;
    width: 10px;
    height: 10px;
    background-color: #061B7F;
}

:deep(.swiper-pagination) .swiper-pagination-bullet.swiper-pagination-bullet-active {
    border: 2px solid #35ACFF;
    box-sizing: border-box;
}

.jiceng-list {
    padding-top: 27px;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
}
.jiceng-item {
    position: relative;
    padding: 38px 16px 16px;
    /* background: #000322; */
    box-sizing: border-box;
    width: 190px;
    height: 80px;
    border: 1px solid rgba(48, 100, 232, 0.3);
    display: flex;
    justify-content: space-between;
    margin-bottom: 30px;
    &:nth-last-child(-n+2) {
        margin-bottom: 15px;
    }


    .jiceng-name {
        position: absolute;
        background: #000322;
        left: 8px;
        top: -13px;
        padding: 3px 8px;
        font-weight: 700;
        font-size: 16px;
        line-height: 21px;
        color: #3064E8;
    }

    .data-item {
        display: flex;
        width: 70px;
        > span:first-child {
            font-weight: 400;
            font-size: 12px;
            line-height: 16px;
            color: #62697D;
            align-self: flex-end;
            margin-right: 6px;
        }
        > span:nth-child(2) {
            width: 40px;
            font-weight: 700;
            font-size: 20px;
            line-height: 26px;
            text-align: right;
            color: #FFFFFF;
        }
    }
}
</style>
