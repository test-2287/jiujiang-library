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
    name: 'ArriveChart',
    components: { VChart, ChartHeader },
    setup() {
        const options = ref({})

        onMounted(() => {
            options.value = {
                grid: {
                    width: '406px',
                    top: '12px',
                    left: '7px',
                    bottom: '5px',
                    containLabel: true,
                },

                xAxis: {
                    type: 'category',
                    data: ['1月', '2月', '3y', '4y', '5y', '6y'],
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
                    show: true,
                    type: 'value',
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
                    name: '到馆人数',
                    nameTextStyle: {
                        align:'left',
                        verticalAlign: 'top',
                        fontSize: 10,
                        lineHeight: 12,
                        padding: [10, 0, 0, 10]
                    },
                    max: function (value) {   
                        return value.max + 10
                    }
                },
                
                series: [
                    {
                        type: 'bar',
                        data: [40, 40, 40, 40, 40, 40],
                        color: {
                            type:'linear',
                            x: 0,
                            y: 1,
                            x2: 0,
                            y2: 0,
                            colorStops:[
                                { offset: 0, color: 'rgba(0, 77, 251, 0)'},
                                { offset: 1, color: 'rgb(0, 77, 251)'},
                            ], 
                        }
                    },
                    {
                        type: 'bar',
                        data: [20, 20, 20, 20, 20, 20],
                        color: {
                            type:'linear',
                            x: 0,
                            y: 1,
                            x2: 0,
                            y2: 0,
                            colorStops:[
                                { offset: 0, color: 'rgba(210, 106, 14, 0)'},
                                { offset: 1, color: 'rgba(210, 106, 14, 1)'},
                            ]
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
    <ChartHeader :title="'市馆到馆人数'"/>
    <div class="arrive-data data-list">
        <div class="item today-arrive">
            <span class="label">今日到馆</span>
            <span class="number">203</span>
        </div>        
        <div class="item now-visitor">
            <span class="label">目前在馆</span>
            <span class="number">203</span>
        </div>
        <div class="item month-visitor">
            <span class="label">本月到馆</span>
            <span class="number">203</span>
        </div>
        <div class="item year-visitor">
            <span class="label">全年到馆</span>
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
    padding: 0 8px;
}

/* .data-list {
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
} */
</style>
