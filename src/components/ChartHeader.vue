<script>
import { defineComponent, defineProps, onMounted, ref } from 'vue';

export default defineComponent ({
    name: 'ChartHeader',
    props: ['title'],
    setup(props){
        let titleRef = ref('')        
        onMounted(() => {
            titleRef.value = props.title
        })

        return {
            titleRef    
        }
    }
    
})
</script>

<template>
<div class="chart-header">
    <i class="header-icon"></i>
    <span class="header-title">{{titleRef}}</span>
</div>
</template>    

<style scoped lang="scss">
.chart-header {
    /* width: 100%; */
    height: 36px;
    background-image: url('/chart-header-left.png'), url('/chart-header-right.png');
    background-size: cover;
    background-repeat: no-repeat;
    position: relative;
    display: flex;
    align-items: center;
    padding-left: 10px;
    .header-icon {
        margin-right: 9px;
        width: 12px;
        height: 12px;
        background-image: url('/icon-chart-header.svg');
        background-size: cover;
        transform: scale(3);
    }
    .header-title {
        font-weight: 900;
        font-size: 18px;
        line-height: 25px;
        background: linear-gradient(180deg, #FFFFFF 11.11%, #4AB0F7 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
        text-shadow: 0px 3px 6px rgba(0, 0, 0, 0.25);
    }
}
</style>