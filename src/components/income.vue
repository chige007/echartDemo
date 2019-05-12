<template>
    <div style="height: 100%;width: 100%;">
        <div ref="chart" style="height: 100%;width: 100%;"></div>
    </div>
</template>
<script>
export default {
    data () {
        return {
            myChart: null,
            options : {
                title: {
                    text: '2019年收入目标进展情况',
                    x:'center',
                    top: 10,
                    textStyle: {
                        fontSize: 26
                    }
                },
                tooltip : {
                    trigger: 'axis',
                    axisPointer : {            // 坐标轴指示器，坐标轴触发有效
                        type : 'shadow'        // 默认为直线，可选为：'line' | 'shadow'
                    }
                },
                legend: {
                    data: ['一月收入', '二月收入','三月收入','四月收入','五月收入'],
                    orient: 'vertical',
                    top: 70,
                    right: 20
                },
                grid: {
                    top: 70,
                    left: 30,
                    right: 140,
                    bottom: '3%',
                    containLabel: true
                },
                xAxis:  {
                    type: 'value',
                    name: '金额',   
                    axisLabel: {
                        formatter: '{value} 万元'
                    }
                },
                yAxis: {
                    type: 'category',
                    data: ['融资担保事业总部', '广州分公司','东莞分公司','产融创新事业总部','保证担保事业总部','零售担保事业部','中山子公司','安徽子公司','云浮子公司','深圳子公司','投资管理部','财务部','资本管理公司','小贷公司','业务管理部','证券事务部'],
                },
                series: [
                    {
                        name: '一月收入',
                        type: 'bar',
                        stack: '总量',
                        label: {
                            normal: {
                                show: true,
                                position: 'insideRight'
                            }
                        },
                        data: [271, 221, 0, 261, 80 ,146 ,161 ,305 ,114 ,51 ,283 ,37 ,49 ,433 ,6, 0 ]
                    },
                    {
                        name: '二月收入',
                        type: 'bar',
                        stack: '总量',
                        label: {
                            normal: {
                                show: true,
                                position: 'insideRight'
                            }
                        },
                        data: [277 ,7 ,0 ,215 ,123 ,146 ,250 ,69 ,8 ,63 ,440 ,8 ,50 ,406 ,12 ,0 ]
                    },
                    {
                        name: '三月收入',
                        type: 'bar',
                        stack: '总量',
                        label: {
                            normal: {
                                show: true,
                                position: 'insideRight'
                            }
                        },
                        data: [871 ,116 ,39 ,180 ,111 ,167 ,170 ,181 ,154 ,123 ,546 ,21 ,0 ,429, 0.2 ,9 ]
                    },
                    {
                        name: '四月收入',
                        type: 'bar',
                        stack: '总量',
                        label: {
                            normal: {
                                show: true,
                                position: 'insideRight'
                            }
                        },
                        data: [490 ,60 ,0 ,135, 214 ,178 ,238 ,68 ,90 ,108 ,401 ,0 ,0 ,480, 3 ,9 ]
                    },
                    {
                        name: '五月收入',
                        type: 'bar',
                        stack: '总量',
                        label: {
                            normal: {
                                show: true,
                                position: 'insideRight'
                            }
                        },
                        data: [37 ,0 ,52 ,56 ,55 ,0 ,20 ,4 ,0 ,87 ,0 ,0 ,0 ,0 ,0 ,0 ]
                    }
                ]
            }
        }
    },
    methods: {
        init () {
            var chart = this.$refs.chart;
            this.myChart = this.$echarts.init(chart);
            this.myChart.setOption(this.options);
            window.addEventListener("resize", () => { 
                this.myChart.resize();
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

