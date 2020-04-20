<template>
	<view>
		<!-- 轮播图 -->
		<swiper class=" screen-swiper square-dot" :indicator-dots="true" :circular="true"
		 :autoplay="true" interval="5000" duration="500">
			<swiper-item>
				<image src="../../static/home/banner_1.png"
				mode="aspectFill"></image>
			</swiper-item>
			<swiper-item>
				<image src="../../static/home/banner_1.png"
				mode="aspectFill"></image>
			</swiper-item>
			<swiper-item>
				<image src="../../static/home/banner_1.png"
				mode="aspectFill"></image>
			</swiper-item>
		</swiper>
		<!-- 我的信息 -->
		<mine-info></mine-info>
		<!-- 功能按钮 -->
		<view class="cu-list grid no-border col-4 theme_bg">
			<view class="cu-item" 
			v-for="item in homeicon" 
			:key="item.id">
				<image :src="item.icon" class="icon" mode="widthFix" ></image>
				<!-- <view :class="['cuIcon-' + item.cuIcon]"></view> -->
				<text class="theme_color">{{item.name}}</text>
			</view>
		</view>
		<!-- 信息板块 -->
		<view class="flex p-xs mb-sm">
			<view class="flex-sub text-center margin-xs padding-sm" :class="'bg-'+item.bg"
			v-for="item in infoList" :key="item.id">
					<view class="margin-xs">{{item.title}}</view>
					<view class="text-xl margin-xs">{{item.number1}}</view>
					<view class="text-lg">
						{{item.number2}}
						<text class="margin-left">{{item.percentage}}%</text>
					</view>
			</view>
		</view>
		<!-- 表格 -->
		<view class="flex p-xs mb-sm margin-top-sm text-grey text-lg padding-bottom-sm"
			style="border-bottom:1upx solid #999">
			<view class="flex-sub text-center">股票代码</view>
			<view class="flex-sub text-center">名称</view>
			<view class="flex-sub text-center">最新价</view>
			<view class="flex-sub text-center">涨跌幅</view>
			<view class="flex-sub text-center">涨跌价</view>
		</view>
		<view class="flex p-xs mb-sm margin-top-lg margin-bottom-lg text-lg"
			v-for="item in sharesData" :key="item.id">
			<view class="flex-sub text-center">{{item.code}}</view>
			<view class="flex-sub text-center">{{item.name}}</view>
			<view class="flex-sub text-center">{{item.newPrice}}</view>
			<view class="flex-sub text-center">{{item.UpdownB}}%</view>
			<view class="flex-sub text-center">{{item.UpdownP}}</view>
		</view>
		<!-- 热门推荐 -->
		<my-title title="热门推荐"></my-title>
		<view v-for="item in hotRecommend" :key="item.id"
			style="border-bottom:15upx solid #1E2227">
			<view class="cu-bar">
				<view class="action text-xl">
					<text class="text-xl">{{item.name}}</text>
					<text class="margin-left-sm margin-right-sm text-grey">{{item.code}}</text>
					<text class="cuIcon-refresharrow" 
					:style="item.status?'transform: rotateZ(180deg)':null"
					:class="item.status?'text-green':'text-red'"></text>
				</view>
			</view>
			<view class="flex p-xs mb-sm" :class="item.status?'text-green':'text-red'">
				<view class="flex-sub text-center margin-xs padding-sm">
					<view class="margin-sm text-grey">最新价</view>
					<view class="text-xxl margin-sm">{{item.newPrice}}</view>
				</view>
				<view class="flex-sub text-center margin-xs padding-sm">
					<view class="margin-sm text-grey">涨跌幅</view>
					<view class="text-xxl margin-sm">{{item.UpdownB}}</view>
				</view>
				<view class="flex-sub text-center margin-xs padding-sm">
					<view class="margin-sm text-grey">涨跌价</view>
					<view class="text-xxl margin-sm">{{item.UpdownP}}</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
import mineInfo from '../../components/mineInfo.vue';
import myTitle from '../../components/myTitle.vue';
export default{
	components:{
		mineInfo,myTitle
	},
	data(){
		return {
			homeicon:[
				{ icon:'../../static/home/trade_icon.png',name:'交易' },
				{ icon:'../../static/home/hold_icon.png',name:'持仓' },
				{ icon:'../../static/home/info_icon.png',name:'资讯' },
				{ icon:'../../static/home/mine_icon.png',name:'我的' }
			],
			infoList:[
				{ title:'恒生指数',number1:2852.55,number2:14.06, percentage:0.5,bg:'green'},
				{ title:'上证指数',number1:2852.55,number2:14.06, percentage:0.5,bg:'red' },
				{ title:'国企指数',number1:2852.55,number2:14.06, percentage:0.5,bg:'red' },
			],
			sharesData:[
				{ code:'01001',name:'小米集团',newPrice:150.34,UpdownB:0.58,UpdownP:-0.05 },
				{ code:'01001',name:'美团点评',newPrice:150.34,UpdownB:0.58,UpdownP:-0.05 }
			],
			hotRecommend:[
				{ name:'腾讯控股',code:'00700',status:true, newPrice:408.6,UpdownB:0.87,UpdownP:-1.80 },
				{ name:'阿里巴巴',code:'00700',status:false, newPrice:408.6,UpdownB:0.87,UpdownP:-1.80 },
				{ name:'腾讯控股',code:'00700',status:true, newPrice:408.6,UpdownB:0.87,UpdownP:-1.80 },
				{ name:'阿里巴巴',code:'00700',status:false, newPrice:408.6,UpdownB:0.87,UpdownP:-1.80 }
			]
		}
	}
}
</script>

<style scoped>
.icon {
	margin:0 auto;
	width:90upx;
}
.info_plate {
	padding:0!important;
}
</style>
