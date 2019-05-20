<template>
    <div style="height: 100%;width: 100%;">
        <div ref="chart" style="height: 100%;width: 100%;"></div>
        <!-- <div ref="chart2" style="height: 30%;width: 100%;"></div> -->
    </div>
</template>
<script>
export default {
    data () {
        return {
            myChart: null,
            myChart2: null,
            options : {
                title: {
                    text: '2019年收入目标进展情况',
                    x:'center',
                    top: 0,
                    textStyle: {
                        fontSize: 22
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
                    top: 30,
                    right: 20
                },
                grid: {
                    top: 30,
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
                        center: ['70%', '67%'],
                        name: '小贷公司年度完成率',
                        type: 'gauge',
                        radius: '40%',
                        data: [{value: 23.45 , name: '小贷公司\n年度完成率成率'}],
                        title: {
                          fontSize: 15  
                        },
                        detail: {
                            fontWeight: 'normal',
                            fontSize: 28,
                            formatter:'{value}%'
                        },
                        axisLine: {            // 坐标轴线
                            lineStyle: {       // 属性lineStyle控制线条样式
                                width: 10
                            }
                        },
                        axisTick: {            // 坐标轴小标记
                            length:15,        // 属性length控制线长
                            lineStyle: {       // 属性lineStyle控制线条样式
                                color: 'auto'
                            }
                        },
                        splitLine: {           // 分隔线
                            length:14,         // 属性length控制线长
                            lineStyle: {       // 属性lineStyle（详见lineStyle）控制线条样式
                                color: 'auto'
                            }
                        },
                        pointer: {
                            width:2
                        }
                    },
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
            },
            options2: {
                tooltip : {
                    formatter: "{a} <br/>{b} : {c}%"
                },
                series: [
                    {
                        center: ['15%', '55%'],
                        name: '小贷公司年度完成率',
                        type: 'gauge',
                        radius: '100%',
                        data: [{value: 43.6, name: '小贷公司年度完成率'}],
                        title: {
                          fontSize: 12  
                        },
                        detail: {
                            fontWeight: 'normal',
                            fontSize: 24,
                            formatter:'{value}%'
                        },
                        axisLine: {            // 坐标轴线
                            lineStyle: {       // 属性lineStyle控制线条样式
                                width: 8
                            }
                        },
                        axisTick: {            // 坐标轴小标记
                            length:2,        // 属性length控制线长
                            lineStyle: {       // 属性lineStyle控制线条样式
                                color: 'auto'
                            }
                        },
                        splitLine: {           // 分隔线
                            length:10,         // 属性length控制线长
                            lineStyle: {       // 属性lineStyle（详见lineStyle）控制线条样式
                                color: 'auto'
                            }
                        },
                        pointer: {
                            width:2
                        }
                    },
                    {
                        center: ['50%', '60%'],
                        name: '资管理部年度完成率',
                        type: 'gauge',
                        radius: '100%',
                        data: [{value: 52.3, name: '资管理部\n年度完成率成率'}],
                        title: {
                          fontSize: 12  
                        },
                        detail: {
                            fontWeight: 'normal',
                            fontSize: 24,
                            formatter:'{value}%'
                        },
                        axisLine: {            // 坐标轴线
                            lineStyle: {       // 属性lineStyle控制线条样式
                                width: 8
                            }
                        },
                        axisTick: {            // 坐标轴小标记
                            length:2,        // 属性length控制线长
                            lineStyle: {       // 属性lineStyle控制线条样式
                                color: 'auto'
                            }
                        },
                        splitLine: {           // 分隔线
                            length:10,         // 属性length控制线长
                            lineStyle: {       // 属性lineStyle（详见lineStyle）控制线条样式
                                color: 'auto'
                            }
                        },
                        pointer: {
                            width:2
                        }
                    },
                    {
                        center: ['90%', '55%'],
                        name: '小贷公司年度完成率',
                        type: 'gauge',
                        radius: '100%',
                        data: [{value: 32.3, name: '融资担保事业总部\n年度完成率成率'}],
                        title: {
                          fontSize: 12  
                        },
                        detail: {
                            fontWeight: 'normal',
                            fontSize: 24,
                            formatter:'{value}%'
                        },
                        axisLine: {            // 坐标轴线
                            lineStyle: {       // 属性lineStyle控制线条样式
                                width: 8
                            }
                        },
                        axisTick: {            // 坐标轴小标记
                            length:2,        // 属性length控制线长
                            lineStyle: {       // 属性lineStyle控制线条样式
                                color: 'auto'
                            }
                        },
                        splitLine: {           // 分隔线
                            length:10,         // 属性length控制线长
                            lineStyle: {       // 属性lineStyle（详见lineStyle）控制线条样式
                                color: 'auto'
                            }
                        },
                        pointer: {
                            width:2
                        }
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
        },
        init2 () {
            var chart = this.$refs.chart2;
            this.myChart2 = this.$echarts.init(chart);
            this.myChart2.setOption(this.options2);
            window.addEventListener("resize", () => { 
                this.myChart2.resize();
            });
        }
    },
    mounted () {
        this.init();
        // this.init2();
        var radarData = [{
            name: '小贷公司年度完成率',
            value: 23.45 
        },{
            name: '资本管理公司\n年度完成率',
            value: 33.85
        },{
            name: '融资担保总部\n年度完成率',
            value: 45.34
        }]
        var index = 0;
        setInterval(() => {
            this.options.series[0].data[0]['value'] = radarData[index]['value'];
            this.options.series[0].data[0]['name'] = radarData[index]['name'];
            this.myChart.setOption(options, true);
            index++;
            if(index == radarData.length)
                index = 0;
        },2000);
    }
}
</script>
<style lang="less" scoped>

</style>

