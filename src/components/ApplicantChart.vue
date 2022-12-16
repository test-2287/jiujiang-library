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
    name: 'ApplicantChart',
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
                    },
                    name: '办证人数',
                    nameTextStyle: {
                        align:'left',
                        verticalAlign: 'top',
                        fontSize: 10,
                        lineHeight: 12,
                        padding: [10, 0, 0, 10]
                    },
                },
                series: [
                    {
                        type: 'line',
                        data: [15, 25, 28, 38, 25, 35],
                        color: '#3064E8',
                        symbolSize: 0,
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
                        // },
                        areaStyle: {
                            color: 'rgba(74, 142, 255, 0.2)'
                        }
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
    <ChartHeader :title="'市馆办证人数'"/>
    <div class="arrive-data data-list">
        <div class="item">
            <span class="label">今日办证</span>
            <span class="number">203</span>
        </div>        
        <div class="item">
            <span class="label">本月办证</span>
            <span class="number">203</span>
        </div>
        <div class="item">
            <span class="label">全年办证</span>
            <span class="number">203</span>
        </div>
        <div class="item">
            <span class="label">全年微信粉丝</span>
            <span class="number">203</span>
        </div>
    </div>
    <VChart :option="options" class="chart"/>  
    </div>
</template>

<style scoped>
.chart{
    width: 406px;
    height: 190px;
}
</style>
