<template>
	<view>
		<!-- 信息板块 -->
		<view class="flex p-xs mb-sm">
			<view class="flex-sub text-center margin-xs padding-sm " :class="'text-'+item.color"
			v-for="item in infoList" :key="item.id">
					<view class="margin-xs text-white">{{item.title}}</view>
					<view class="text-xl margin-xs">{{item.number1}}</view>
					<view class="text-lg">
						{{item.number2}}
						<text class="margin-left">{{item.percentage}}%</text>
					</view>
			</view>
		</view>
		<!-- 表格 -->
		<view class="flex p-xs mb-sm padding-top text-grey padding-bottom"
			style="background-color:#2B2A3A">
			<view class="flex-sub text-center">名称/代码</view>
			<view class="flex-sub text-center">类型/数量</view>
			<view class="flex-sub text-center">手续费/总价</view>
			<view class="flex-sub text-center">成交/现价</view>
			<view class="flex-sub text-center">留仓/盈亏	</view>
		</view>
		<view class="flex p-xs mb-sm padding-top text-grey  padding-bottom"
			style="border-bottom:3upx solid #999" v-for="item in tableData" :key="item.id">
			<view class="flex-sub text-center">{{item.name}}<br>{{item.code}}</view>
			<view class="flex-sub text-center">{{item.type}}<br>{{item.number}}</view>
			<view class="flex-sub text-center">{{item.commission}}<br>{{item.total}}</view>
			<view class="flex-sub text-center">{{item.deal}}<br>{{item.currentPrice}}</view>
			<view class="flex-sub text-center">{{item.liucang}}<br>{{item.yingkui}}</view>
		</view>
	</view>
</template>

<script>
export default {
	data(){
		return {
			infoList:[
				{ title:'恒生指数',number1:2852.55,number2:14.06, percentage:0.5,color:'green'},
				{ title:'上证指数',number1:2852.55,number2:14.06, percentage:0.5,color:'red' },
				{ title:'国企指数',number1:2852.55,number2:14.06, percentage:0.5,color:'red' },
			],
			tableData:[
				{ 
					name:'小米集团',code:'123456',
					type:'类型A',number:23,
					commission:120,total:1200,
					deal:1320,currentPrice:1000,
					liucang:500,yingkui:240
				},
				{
					name:'美团点评',code:'123456',
					type:'类型B',number:23,
					commission:120,total:1200,
					deal:1320,currentPrice:1000,
					liucang:500,yingkui:240
				},
			]
		}
	}
}
</script>

<style>
</style>
