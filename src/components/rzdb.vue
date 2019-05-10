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
                title : [{
                    text: '集团融资担保小微\n企业500万以下占比',
                    textStyle: {
                        fontSize: 18
                    },
                    textAlign: 'center',
                    top: '46%',
                    left: '27%'
                },{
                    text: '2019年\n集团融资担保存量业务\n企业类型占比情况',
                    textStyle: {
                        fontSize: 18,
                    },
                    textAlign: 'center',
                    top: '44%',
                    left: '74.5%'
                },{
                    text: '集团融资担保业务小微企业占比指标',
                    x:'center',
                    textStyle: {
                        fontSize: 26
                    },
                    top: 10,
                }],
                tooltip : {
                    trigger: 'item',
                    formatter: "{a} <br/>{b} : {c} ({d}%)"
                },
                toolbox: {
                    show : true,
                    feature : {
                        mark : {show: true},
                        dataView : {show: true, readOnly: false},
                        magicType : {
                            show: true,
                            type: ['pie', 'funnel']
                        },
                        restore : {show: true},
                        saveAsImage : {show: true}
                    }
                },
                calculable : true,
                series : [
                    {
                        name:'半径模式',
                        type:'pie',
                        radius : [90, 150],
                        center : ['28%', '50%'],
                        data:[
                            {value:48345, name:'单户500及以下'},
                            {value:155886, name:'单户500以上'}
                        ],
                        label: {
                            formatter: '{b}\n{c}\n{d}%'
                        }
                    },
                    {
                        name:'面积模式',
                        type:'pie',
                        radius : [90, 150],
                        center : ['75%', '50%'],
                        data:[
                            {value:12162, name:'个人'},
                            {value:13740, name:'微型'},
                            {value:190491, name:'小型'},
                            {value:55324, name:'中型'},
                            {value:2000, name:'大型'}
                        ],
                        label: {
                            formatter: '{b}\n{c}\n{d}%'
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

