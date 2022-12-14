<script>
import ChartHeader from './ChartHeader.vue'
import { defineComponent } from 'vue';

import { Swiper, SwiperSlide } from 'swiper/vue'
import { Autoplay } from 'swiper'
import 'swiper/css';

export default defineComponent({
    name: 'NewBooks',
    components: { ChartHeader, Swiper, SwiperSlide },
    setup() {
        return { 
            modules: [Autoplay] 
        }
    }
})
</script>

<template>
    <div class="sub-chart-container">
        <ChartHeader :title="'新书推荐'"/>
        <div class="new-books-list">
        <swiper :modules="modules"
                :slidesPerView="3"
                :loop="true"
                :autoplay="{
                    deplay: 3000
                }"
        >

            <SwiperSlide>
            <div class="new-book-item">
                <div class="book-image">
                    <img src="/book-bofuwa.png" alt="">
                </div>
                <span class="book-name">成为波伏娃</span>
                <span class="book-author">
                    [英]凯特·柯克帕特..
                    <br>
                    中信出版社
                </span>
            </div>
        </SwiperSlide>

            <SwiperSlide>
            <div class="new-book-item">
                <div class="book-image">
                    <img src="/book-bofuwa.png" alt="" />
                </div>
                <span class="book-name">成为波伏娃</span>
                <span class="book-author">
                    [英]凯特·柯克帕特..
                    <br>
                    中信出版社
                </span>
            </div>
            </SwiperSlide>

            <SwiperSlide>
            <div class="new-book-item">
                <div class="book-image">
                    <img src="/book-bofuwa.png" alt="" />
                </div>
                <span class="book-name">成为波伏娃</span>
                <span class="book-author">
                    [英]凯特·柯克帕特..
                    <br>
                    中信出版社
                </span>
            </div>
            </SwiperSlide>

            <SwiperSlide>
            <div class="new-book-item">
                <div class="book-image">
                    <img src="/book-hamelton.png" alt="">
                </div>
                <span class="book-name">成为波伏娃</span>
                <span class="book-author">
                    [英]凯特·柯克帕特..
                    <br>
                    中信出版社
                </span>
            </div>
        </SwiperSlide>

            <SwiperSlide>
            <div class="new-book-item">
                <div class="book-image">
                    <img src="/book-hamelton.png" alt="" />
                </div>
                <span class="book-name">成为波伏娃</span>
                <span class="book-author">
                    [英]凯特·柯克帕特..
                    <br>
                    中信出版社
                </span>
            </div>
        </SwiperSlide>

            <SwiperSlide>
            <div class="new-book-item">
                <div class="book-image">
                    <img src="/book-hamelton.png" alt="" />
                </div>
                <span class="book-name">成为波伏娃</span>
                <span class="book-author">
                    [英]凯特·柯克帕特..
                    <br>
                    中信出版社
                </span>
            </div>
            </SwiperSlide>

            <SwiperSlide>
            <div class="new-book-item">
                <div class="book-image">
                    <img src="/book-maboyong.png" alt="">
                </div>
                <span class="book-name">成为波伏娃</span>
                <span class="book-author">
                    [英]凯特·柯克帕特..
                    <br>
                    中信出版社
                </span>
            </div>
        </SwiperSlide>

            <SwiperSlide>
            <div class="new-book-item">
                <div class="book-image">
                    <img src="/book-maboyong.png" alt="" />
                </div>
                <span class="book-name">成为波伏娃</span>
                <span class="book-author">
                    [英]凯特·柯克帕特..
                    <br>
                    中信出版社
                </span>
            </div>
        </SwiperSlide>

            <SwiperSlide>
            <div class="new-book-item">
                <div class="book-image">
                    <img src="/book-maboyong.png" alt="" />
                </div>
                <span class="book-name">成为波伏娃</span>
                <span class="book-author">
                    [英]凯特·柯克帕特..
                    <br>
                    中信出版社
                </span>
            </div>
            </SwiperSlide>

        </swiper>
        </div>
    </div>
</template>

<style scoped lang="scss">


:deep(.swiper-slide) {
    display: flex;
}
.new-books-list{
    padding: 25px 12px 16px;
    display: flex;
    .new-book-item {
        padding: 10px;
        padding-bottom: 12px;
        display: flex;
        flex-direction: column;
        width: 132px;
        box-sizing: border-box;
        .book-image {
            margin-bottom: 16px;
            width:100px ;
            height: 142px;
            border: 1px solid rgba(48, 100, 232, 0.3);
            filter: drop-shadow(6px 6px 12px rgba(74, 142, 255, 0.25));
            img {
                width: 100%;
                height: 100%;
            }
        }
        .book-name {
            margin-bottom: 7px;
            font-weight: 700;
            font-size: 16px;
            line-height: 21px;
            color: #FFFFFF;
        }
        .book-author {
            font-size: 12px;
            line-height: 16px;
            color: #62697D;
        }

    }
}
</style>