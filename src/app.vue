<template>
<div class="layout">
	<div class="menu list-group">
        <span v-for="x in menus" class="list-group-item" :class="{active: x.code == current_menu}" @click="menusClick(x.code)">{{x.text}}</span>
    </div>
    <div class="demo">
        <bzdbzbfbqk v-if="current_menu == 'bzdbzbfbqk'"></bzdbzbfbqk>
        <general-income v-if="current_menu == 'generalIncome'"></general-income>
        <rzdb v-if="current_menu == 'rzdb'"></rzdb>
    </div>
</div>
</template>

<script>
import generalIncome from './components/generalIncome.vue';
import bzdbzbfbqk from './components/bzdbzbfbqk.vue';
import rzdb from './components/rzdb.vue';
export default {
	props : {
	},
	computed : {
	},
	components : {
        bzdbzbfbqk,
        generalIncome,
        rzdb
	},
	data : () => {
		return {
            current_menu: 'generalIncome',
            menus: [{
                code: 'generalIncome',
                text: '公司总部、各子公司总收入'
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
        .menu{
            position: absolute;
            left: 20px;
            top: 20px;
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