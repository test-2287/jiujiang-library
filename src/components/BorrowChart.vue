<script>
import * as echarts from 'echarts'
import { use } from 'echarts/core'
import { CanvasRenderer } from 'echarts/renderers'
import { defineComponent, onMounted, ref } from 'vue'
import VChart from 'vue-echarts'

import ChartHeader from '../components/ChartHeader.vue'

use([
    CanvasRenderer
])

export default defineComponent({
    name: 'BorrowChart',
    components: { VChart, ChartHeader },
    setup() {
        const options = ref({})

        onMounted(() => {
            options.value = {
                grid: {
                    width: '380px',
                    height: '145px',
                    top: '26px',
                    left: '20px'
                },
                xAxis: {
                    data: ['1月', '2月', '3', '4', '5', '6'],
                    axisLine:{
                        lineStyle: {
                            color: 'rgba(255, 255, 255, 0.2)'
                        }
                    },
                    axisLabel: {
                        show: true
                    },
                    splitLine:{
                        show: false,
                        lineStyle:{
                            color: 'rgba(255, 255, 255, 0.2)'
                        } 
                    },
                    axisTick: {
                        show: false
                        // inside: true
                    },
                },
                yAxis: {
                    axisLine:{
                        show: true,
                        lineStyle: {
                            color: 'rgba(255, 255, 255, 0.2)'
                        }
                    },
                    // axisTickk: {
                    //     show: true
                    // },
                    splitLine:{
                        show: true,
                        lineStyle:{
                            color: 'rgba(255, 255, 255, 0.05)'
                        } 
                    }
                },
                series: [
                    {
                        type: 'line',
                        data: [15, 25, 28, 38, 25, 35],
                        color: '#3064E8',
                        symbolSize: 6,
                        symbol: 'circle',
                        symbolColor:'#3064E8', 
                        itemStyle: {
                            color: '#3064E8'
                        },
                        lineStyle: {
                            width: 2
                        },
                        // markPoint:{
                        //     symbol: 'circle',
                        //     symbolSize: 6
                        // }
                    },
                    {
                        type: 'line',
                        data: [8, 14, 12, 10, 15, 11],
                        color: '#D26A0E',
                        lineStyle: {
                            width: 2
                        },
                        symbolSize: 6,
                        symbol: 'circle',

                    }
                ]
            }

        })

        return { options }
    }
})

</script>

<template>
    <div class="sub-chart-container">
    <ChartHeader :title="'市馆借阅数据'"/>
    <div class="arrive-data data-list">
        <div class="item borrow">
            <span class="label">今日借阅</span>
            <span class="number">203</span>
        </div>        
        <div class="item return">
            <span class="label">今日还书</span>
            <span class="number">203</span>
        </div>
        <div class="item">
            <span class="label">本月借阅</span>
            <span class="number">203</span>
        </div>
        <div class="item">
            <span class="label">全年借阅</span>
            <span class="number">203</span>
        </div>
    </div>
    <VChart :option="options" class="chart"/>  
    </div>
</template>

<style scoped lang="scss">
.chart{
    width: 406px;
    height: 190px;
}

.data-list {
    .item.borrow .label::after{
        margin-left: 10px;
        margin-top: -2px;
        content: '';
        width: 10px;
        height: 10px;
        background-color: #3064E8;
        border-radius: 50%;
    }

    .item.return .label::after{
        margin-left: 10px;
        margin-top: -2px;
        content: '';
        width: 10px;
        height: 10px;
        background-color: #D26A0E;
        border-radius: 50%;
    }
}
</style>
