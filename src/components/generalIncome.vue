<template>
    <div style="height: 100%;width: 100%;">
        <div ref="chart" style="height: 100%;width: 100%;"></div>
    </div>
</template>
<script>
export default {
    data () {
        return {
            options : {
                title: {
                    text: '公司总部、各子公司总收入',
                    x:'center',
                    top: 10,
                    textStyle: {
                        fontSize: 26
                    }
                },
                grid: {
                    top: 160,
                    left: 100,
                    right: 80,
                    bottom: 30
                },
                tooltip: {
                    trigger: 'axis',
                    axisPointer: {
                        type: 'cross',
                        crossStyle: {
                            color: '#999'
                        }
                    }
                },
                toolbox: {
                    feature: {
                        dataView: {show: true, readOnly: false},
                        magicType: {show: true, type: ['line', 'bar']},
                        restore: {show: true},
                        saveAsImage: {show: true}
                    },
                    top: 75,
                    right: 30
                },
                legend: {
                    data:['18年集团收入','19年集团收入','同比增长'],
                    top: 80,
                },
                xAxis: [
                    {
                        type: 'category',
                        data: ['公司总部','中山公司','安徽公司','云浮公司','深圳公司','小贷公司','合计收入'],
                        axisPointer: {
                            type: 'shadow'
                        }
                    }
                ],
                yAxis: [
                    {
                        type: 'value',
                        name: '金额',
                        // min: 0,
                        // max: 250,
                        // interval: 50,    
                        axisLabel: {
                            formatter: '{value} 万元'
                        }
                    },
                    {
                        type: 'value',
                        name: '百分比',
                        // min: 0,
                        // max: 25,
                        // interval: 5,
                        axisLabel: {
                            formatter: '{value} %'
                        }
                    }
                ],
                series: [
                    {
                        name:'18年集团收入',
                        type:'bar',
                        label: {
                            normal: {
                                show: true,
                                position: 'top'
                            }
                        },
                        data:[3404, 650, 572, 84, 0, 1277, 5985],
                        barWidth: '20%',
                        itemStyle: {
                            barBorderRadius: [100, 100, 0, 0],
                            color: '#7189bf'
                        }
                    },
                    {
                        name:'19年集团收入',
                        type:'bar',
                        label: {
                            normal: {
                                show: true,
                                position: 'top'
                            }
                        },
                        data:[4693, 681, 555, 276, 237, 1268, 7608],
                        barWidth: '20%',
                        itemStyle: {
                            barBorderRadius: [100, 100, 0, 0],
                            color: '#ee7777'
                        }
                    },
                    {
                        name:'同比增长',
                        type:'line',
                        yAxisIndex: 1,
                        data:[38, -11, -3, 203, 100, -1, 27],
                        itemStyle: {
                            color: '#49beb7'
                        }
                    }
                ]
            }
        }
    },
    methods: {
        init () {
            var chart = this.$refs.chart;
            var myChart = this.$echarts.init(chart);
            myChart.setOption(this.options);
            window.addEventListener("resize", () => { 
                myChart.resize();
            });
        }
    },
    mounted () {
        this.init();
    }
}
</script>
<style lang="less" scoped>

</style>

