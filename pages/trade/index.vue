<template>
	<view>
		<!-- 搜索 -->
		<view class="cu-bar search">
			<view class="search-form round">
				<text class="cuIcon-search"></text>
				<input @focus="InputFocus" @blur="InputBlur" :adjust-position="false" 
				type="text" placeholder="搜索股票代码或者拼音文字简称" confirm-type="search"></input>
			</view>
			<view class="action">
				<button class="cu-btn bg-blue shadow-blur round">搜索</button>
			</view>
		</view>
		<!-- 标题 -->
		<my-title title="热门搜索"></my-title>
		<view class="flex p-xs mb-sm padding-top-xl padding-bottom-xl text-grey text-lg"
			style="border-bottom:1upx solid #999999" v-for="item in dataList" :key="item.id">
			<view class="flex-sub text-center">{{item.name}}</view>
			<view class="flex-sub text-center">{{item.code}}</view>
			<view class="flex-sub text-center">{{item.title}}</view>
			<view class="flex-sub text-center">
				<text class="text-red" :class="item.status?'cuIcon-likefill':'cuIcon-like'"
				style="font-size:40upx"></text>
			</view>
		</view>
	</view>
</template>

<script>
import myTitle from '../../components/myTitle.vue';
export default {
	components:{
		myTitle
	},
	data(){
		return {
			dataList:[
				{ name:'HK',code:'834902',title:'小米集团',status:false },
				{ name:'HK',code:'834902',title:'美团点评',status:true }
			]
		}
	}
}
</script>

<style>
</style>
