<template>
<div class="layout" :class="{isCollapse: collapse}">
    <button class="btn btn-default collapseBtn" @click="doCollapse"><i class="glyphicon" :class="{'glyphicon-chevron-left': !collapse, 'glyphicon-chevron-right': collapse}"></i></button>
	<div class="menu list-group" v-show="!collapse">
        <span v-for="x in menus" class="list-group-item" :class="{active: x.code == current_menu}" @click="menusClick(x.code)">{{x.text}}</span>
    </div>
    <div class="demo">
        <bzdbzbfbqk v-if="current_menu == 'bzdbzbfbqk'"></bzdbzbfbqk>
        <general-income v-if="current_menu == 'generalIncome'"></general-income>
        <rzdb v-if="current_menu == 'rzdb'"></rzdb>
        <income v-if="current_menu == 'income'"></income>
    </div>
</div>
</template>

<script>
import generalIncome from './components/generalIncome.vue';
import bzdbzbfbqk from './components/bzdbzbfbqk.vue';
import rzdb from './components/rzdb.vue';
import income from './components/income.vue';
export default {
	props : {
	},
	computed : {
	},
	components : {
        bzdbzbfbqk,
        generalIncome,
        rzdb,
        income
	},
	data : () => {
		return {
            current_menu: 'generalIncome',
            collapse: false,
            menus: [{
                code: 'generalIncome',
                text: '公司总部、各子公司总收入'
            },{
                code: 'income',
                text: '2019年收入目标进展情况'
            },{
                code: 'bzdbzbfbqk',
                text: '保证担保在保分布情况'
            },{
                code: 'rzdb',
                text: '集团融资担保业务小微企业占比指标'
            }]
		};
    },
	methods : {
        menusClick (code) {
            this.$set(this.$data, 'current_menu', code);
        },
        doCollapse () {
            this.collapse = !this.collapse;
            this.$nextTick(() => {
                this.$children[0].myChart.resize();
            });
        }
	},
	mounted  () {
        
	}
} 
</script>

<style lang="less" scoped>
    .layout{
        width: 100%;
        height: 100%;
        padding: 30px 30px 30px 300px;
        &.isCollapse{
            padding: 30px 30px 30px 60px;
        }
        .collapseBtn{
            position: absolute;
            left: 20px;
            top: 20px;
            padding: 5px 8px;
        }
        .menu{
            position: absolute;
            left: 20px;
            top: 65px;
            .list-group-item{
                cursor: pointer;
                &:hover{
                    background-color: #f7f7f7;
                }
                &.active{
                    &:hover{
                        background-color: #337ab7;
                    }
                }
            }
        }
        .demo{
            height: 100%;
            width: 100%;
        }
    }
</style>