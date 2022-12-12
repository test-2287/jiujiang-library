<script setup>
import HelloWorld from './components/HelloWorld.vue'
import CenterMap from './components/CenterMap.vue'
import ArriveChart from './components/ArriveChart.vue'
import BorrowChart from './components/BorrowChart.vue'
import ApplicantChart from './components/ApplicantChart.vue'
import ChartHeader from './components/ChartHeader.vue'
import JicengBorrow from './components/JicengBorrow.vue'
import BookBorrowList from './components/BookBorrowList.vue'
import NewBooks from './components/NewBooks.vue'

import {onMounted, onUnmounted, ref} from 'vue'

const mapDistricData = ref({
  name: '濂溪区', value: { bookBorrowNum: 210, enterNum: 50, applicants: 30, bookNum: 53454 },
})

const videoArr = ["http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4", 
"http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/ElephantsDream.mp4", 
"http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/ForBiggerEscapes.mp4"]
let curVideo = 0

const hightlight = (event) => {
  // console.log(11111);
  // console.log(event);
  mapDistricData.value = event.data
}

const videoEnd = () => {
  curVideo++;
  if (curVideo >= videoArr.length) {
    curVideo = 0
  }
}

const centerNumber1 = ref(null)
const centerNumber2 = ref(null)
const centerNumber3 = ref(null)
const value1 = 3514674;
      const value2 = 4282;
      const value3 = 2489;
      const time = 2


const numberGrow = (ele, value) => {
        // debugger;
        //【这里调速度 1 ，步进值， 通俗地讲，就是每次跳的时候，增加的一个增量】
        let step = parseInt((value * 100) / (time * 1000));
        // 设置当前值(这个值是计时器持续运行时，每次页面上显示的跳动值，不是最终的那个具体值)
        let current = 0
        // 设置开始值
        let start = 0
        // 设置定时器，用来反复横跳的，哈哈哈
        let t = setInterval(() =>{
          // 每次增加一点步进值
          start += step
          // 开始值大于传过来的的值，说明 到点了，不用 继续横跳了
          if (start > value) {
            clearInterval(t)
            // 把穿过的值赋给start，结束
            start = value
            // 清掉计时器
            t = null
          }
          if(start == 0){
            start = value;
            clearInterval(t)
          }
          // 当前值等于开始值，那就结束
          if (value === 0) {
          return
          }
          current = start
          // 正则
          ele.innerHTML = current.toString().replace(/(\d)(?=(?:\d{3}[+]?)+$)/g, '$1,')
        }, time * 100)  // 【这里调速度 2， 通俗地讲，这里是页面上，肉眼能看到的跳动频率】
        // 本来想设置成 秒 *1000的，但是实在太慢了，就改成 *100了
      }


      onMounted(() => {
        numberGrow(centerNumber1.value, value1)
        numberGrow(centerNumber2.value, value2)
        numberGrow(centerNumber3.value, value3)
      })


let bulletinTimer = null
let bulletinActive = ref(true)
onMounted(() => {
  bulletinTimer = setInterval(() => {
    bulletinActive.value = !bulletinActive.value
  }, 4000)
})
onUnmounted(() => {
  clearInterval(bulletinTimer)
})


</script>

<template>
  <!-- <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div> -->
  <!-- <HelloWorld msg="Vite + Vue" /> -->

  <!-- <CenterMap /> -->

  <div class="top-bar">
    <div class="date-time">
      <i class="icon-calender"></i>
      <div class="time">
        <span>2022年12月12日</span>
        <span>星期三</span>
        <span>10:20</span>
      </div>
    </div>
    <div class="page-title"></div>
    <div class="today-weather">
      <span class="label">今日天气</span>
      <span class="info">晴转多云 5°-10°C</span>
    </div>
  </div>
  <div class="charts-container">
    <div class="left">
      <ArriveChart />
      <BorrowChart />
      <ApplicantChart />
    </div>
    <div class="center">
      <div class="center-top">
        <div class="center-data">
          <div class="data-item">
            <span class="data-name item-all-books">全市藏书(册)</span>
            <span class="data-num" ref="centerNumber1" :data-time="time" :data-value="value1">0</span>
          </div>
          <div class="data-item">
            <span class="data-name item-new-books">全市年新增书籍</span>
            <span class="data-num" ref="centerNumber2" :data-time="time" :data-value="value2">0</span>
          </div>
          <div class="data-item">
            <span class="data-name item-all-applicants">全市办证数量</span>
            <span class="data-num" ref="centerNumber3" :data-time="time" :data-value="value3">0</span>
          </div>
        </div>
        <CenterMap @hightlight="hightlight"/>
        <div class="map-data">
          <span class="district-data-name">{{mapDistricData.name}}图书馆</span>
          <div class="data-item">
            <span class="item-name">今日借阅册次</span>
            <span class="item-num">{{mapDistricData.value.bookBorrowNum}}</span>
          </div>
          <div class="data-item">
            <span class="item-name">今日借阅册次</span>
            <span class="item-num">{{mapDistricData.value.applicants}}</span>
          </div>
          <div class="data-item">
            <span class="item-name">今日借阅册次</span>
            <span class="item-num">{{mapDistricData.value.enterNum}}</span>
          </div>
          <div class="data-item">
            <span class="item-name">今日借阅册次</span>
            <span class="item-num">{{mapDistricData.value.bookNum}}</span>
          </div>
        </div>
      </div>
      <div class="center-bottom">
        <div class="left">
          <div class="header">
            <span :class="{'active': bulletinActive}" style="margin-left: 93px">通知公告</span>
            <span :class="{'active': !bulletinActive}" style="margin-right:90px">历史上的九江</span>
          </div>
          <div :class="{'active': bulletinActive}" class="bulletin">
            <div  class="date-title">
              <div class="date-box">
                <span class="month">11月</span>
                <span class="date">20</span>
              </div>
              <div class="title">关于开展对设区市人民政府履行教育职责督导评价满意度调查的通知</div> 
            </div>
            <div class="content">
              根据《江西省人民政府教育督导委员会关于印发〈2022年对设区市人民政府履行教育职责督导评价工作实施方案〉的通知》（赣教督委字〔2022〕6号）要求，为广泛了解社情民意，客观、公正、科学地评价设区市人民政府履行教育职责情况，经研究，决定开展设区市人民政府履行教育职责督导评价满意度调查。
            </div>
          </div>
          <div class="history" :class="{'active': !bulletinActive}">

          </div>
        </div>
        <div class="right">
          <div class="video">
            <video :src="videoArr[curVideo]" :autoplay="true" controls @ended="videoEnd"></video>
          </div>
          <span class="video-text">九江市历史宣传片</span>
          <span class="bullets" v-if="videoArr.length">
            <i></i>
            <i></i>
            <i></i>
          </span>
        </div>
      </div>
    </div>
    <div class="right">
      <JicengBorrow />
      <BookBorrowList />
      <NewBooks />
    </div>
  </div>

</template>

<style lang="scss">
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}

.top-bar{
  width: 100%;  
  height: 103px;
  background-image: url('/top-bar.png');
  background-size: contain;
  position: relative;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 33px;
  box-sizing: border-box;
  .page-title {
    width: 782px;
    height: 36px;
    background-image: url('/page-title-font.svg');
    background-size: cover;
    margin: 0 auto;
  }
  .date-time {
    display: flex;
    .icon-calender{
      width: 24px;
      height: 24px;
      background-image: url('/icon-calender.svg');
      background-size: cover;
    }
    .time {
      font-size: 18px;
      line-height: 24px;
      color: #3064E8;
      display: flex;
      > span {
        margin-right: 15px;
      }
    }
  }
  .today-weather {
    display: flex;
    .label {
      margin-right: 15px;
      font-weight: 700;
      font-size: 18px;
      line-height: 24px;
      background: linear-gradient(180deg, #FFFFFF 11.11%, #4AB0F7 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }
    .info {
      font-size: 18px;
      line-height: 24px;
      color: #3064E8;
    }
  }

}

.charts-container {
  box-sizing: border-box;
  padding: 0 30px;
  padding-bottom: 30px;
  height: calc(100% - 103px);
  display: flex;

  .left, .right {
    /* width: calc((100% - 3*24px) / 4); */
    box-sizing: border-box;
    width: 447px;
    height: 100%;
    margin-top: -3px;
    padding: 12px;
    padding-bottom: 17px;
    background: rgba(0, 2, 24, 0.6);
  }
  .center {
    flex: 1;
    display: flex;
    flex-direction: column;
    height: 100%;
    display: flex;

    .center-top {
      position: relative;
      flex:1;
    }

    .center-bottom {
      width: 100%;
      height: 307px;
      align-self: flex-end;
      display: flex;
      padding: 0 24px;
      padding-top: 23px; 
      box-sizing: border-box;
      .left {
        margin-right: 24px;
        padding-bottom: 20px;
        .header {
          display: flex;
          align-items: center;
          justify-content: space-between;
          height: 36px; 
          margin-bottom: 15px;
          > span{
            background: linear-gradient(270deg, rgba(0, 10, 86, 0) 2.08%, #000A56 20.83%, #000A56 48.44%, #000A56 81.77%, rgba(0, 10, 86, 0) 100%);
          font-weight: 900;
          font-size: 18px;
          line-height: 25px;
          background: linear-gradient(180deg, rgba(74, 142, 255, 0) 0%, rgba(74, 142, 255, 0.2) 100%), #182AAC;
          -webkit-background-clip: text;
          -webkit-text-fill-color: transparent;
          background-clip: text;
          text-shadow: 0px 3px 6px rgba(0, 0, 0, 0.25); 

          position: relative;

          &.active {
            background: linear-gradient(180deg, #FFFFFF 11.11%, #4AB0F7 100%);
            -webkit-background-clip: text;
          -webkit-text-fill-color: transparent;
          background-clip: text;
          &::before, &::after {
            content: '';
            width: 5px;
            height: 5px;
            border: 1px solid #4A8EFF;
            transform: rotate(-45deg);
            position: absolute;
            top: 50%;
            transform: rotate(-45deg) translateY(-100%);
          }
          &::before {
            left: -17px;
          }
          &::after {
            right: -24px
          }
          }}
        }
        .bulletin {
          .date-title {
            margin-bottom: 13px;
            display: flex;
            .date-box {
              flex-shrink: 0;
              margin-right: 14px;
              width: 50px;
              height: 50px; 
              background: rgba(48, 100, 232, 0.2);
              display: flex;
              flex-direction: column;
              align-items: center;
              color: #3064E8;
              .month {
                font-size: 12px;
                line-height: 24px;
              }
              .date {
                font-size: 24px;
                line-height: 24px;
                font-weight: 700;
              }
            }
            .title {
              color:#3064E8; 
              font-weight: 700;
              font-size: 16px;
              line-height: 24px;
            }
          }
          .content {
            padding: 0 12px;
            font-family: 'Microsoft YaHei';
            font-weight: 400;
            font-size: 14px;
            line-height: 24px;
            color:#AFC4F9;  
          }
        }

        .bulletin, .history {
          display: none;
          &.active { display: block;}
        }
      }

      .right {
        padding: 24px 18px 33px;
        position: relative;
        .video {
          height: 220px;
          video {
            width: 100%
          }
        }
        .video-text {
          position: absolute;
          left: 18px;
          bottom: 33px;
          font-family: 'Microsoft YaHei';
          font-size: 14px;
          line-height: 18px;
          color: #FFFFFF;
        }
      }
    }
  }
}

.sub-chart-container {
  margin-bottom: 24px;
  &:last-child {
    margin-bottom: 0; 
  }
}

.sub-chart-container .data-list {
    padding-top: 15px;
    display: flex;
    .item {
        flex: 1;
        padding-left: 10px;
        padding-bottom: 4px;
        margin-top: -5px;
        border-left: 1px solid rgba(74, 142, 255, 0.3);
        position: relative;
        color: #3064E8;
        font-size: 14px;
        display: flex;
        flex-direction: column;
        &::after {
            position: absolute;
            width: 2px;
            height: 4px;  
            background-color: #4A8EFF;
            content: '';
            top: 0;
            left: -1px;
        }
    }
    .label {
        color: #3064E8;
        font-size: 14px;
    }
    .number {
        font-weight: 700;
        font-size: 20px;
        color: #fff;
    }
}

.map-data{
  position: absolute;
  box-sizing: border-box;
  width: 447px;
  height: 140px;
  background-image: url('/map-info-bg.png');
  background-size: cover;
  right: 24px;
  bottom: 0;
  padding: 15px 30px 28px;
  display: grid;
  grid-template-columns: repeat(2, 1fr); 
  column-gap: 37px;
  .district-data-name {
    position: absolute;
    font-weight: 700;
    font-size: 24px;
    line-height: 32px;
    /* text-align: right; */
    color: #FFFFFF;
    right: 6px;
    top: -47px;
  }
  .data-item {
    padding: 12px 0;
    border-bottom: 1px solid rgba(74, 142, 255, 0.3);
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: relative;
    &::after {
      position: absolute;
      width: 5px;
      height: 1px;
      background-color: #4A8EFF;
      bottom: 0;
      left:0;
      content: '';
    }
    .item-name {
      font-weight: 700;
      font-size: 14px;
      line-height: 18px;
      color: #3064E8;
    }
    .item-num {
      font-weight: 700;
      font-size: 18px;
      line-height: 24px;
      text-align: right;
      color: #FFFFFF;
    }
  }
}

.center-data {
    position: absolute;
    width: 100%;
    padding: 30px;
    padding-bottom: 0;
    top: 0;
    display: flex;
    justify-content: space-between;
    box-sizing: border-box;
    z-index: 1000;
    .data-item {
      width: 302px;
      height: 132px;
      background-image: url('/center-data-bg.png');
      background-size: cover;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      transform: translateZ(0);
      .data-name {
        font-size: 16px;
        line-height: 21px;
        color: #3064E8;
        margin-bottom: 5px;
        margin-top: -18px;
      }
      .data-num {
        font-weight: 700;
        font-size: 32px;
        line-height: 42px;
        text-align: center;
        color: #FFFFFF;
      }
    }
}
</style>
