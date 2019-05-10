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
                    text: '保证担保在保分布情况',
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
                    data:['18年第一季度','19年第一季度','同比增长'],
                    top: 80,
                },
                xAxis: [
                    {
                        type: 'category',
                        data: ['保证总部','融担总部','东莞','广州','安徽','中山','云浮','总计'],
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
                        name:'18年第一季度',
                        type:'bar',
                        data:[438347, 41914, 1544, 19905, 161793, 165303, 5376, 834184],
                        barWidth: '20%',
                        label: {
                            normal: {
                                show: true,
                                position: 'top'
                            }
                        },
                        itemStyle: {
                            barBorderRadius: [100, 100, 0, 0],
                            color: '#5588a3'
                        }
                    },
                    {
                        name:'19年第一季度',
                        type:'bar',
                        data:[339954, 28428, 107, 12152, 179311, 257246, 25449, 846782],
                        barWidth: '20%',
                        label: {
                            normal: {
                                show: true,
                                position: 'top'
                            }
                        },
                        itemStyle: {
                            barBorderRadius: [100, 100, 0, 0],
                            color: '#d65a31'
                        }
                    },
                    {
                        name:'同比增长',
                        type:'line',
                        yAxisIndex: 1,
                        data:[-22, -32, -93, -39, 11, 56, 373, 2],
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

