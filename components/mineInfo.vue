<template>
	<view class="mine_info padding">
		<!-- one -->
		<view class="flex p-xs mb-sm">
			<view class="flex-sub padding-left">
				<view class="cu-avatar round" style="background-image:url(https://ossweb-img.qq.com/images/lol/web201310/skin/big81005.jpg);"></view>
			</view>
			<view class="flex-twice theme_center row_center text-lg">
				交易账号
			</view>
			<view class="flex-treble theme_center row_center text-lg">
				{{userinfo.username}}
			</view>
		</view>
		<!-- tow -->
		<view class="flex p-xs mb-sm margin-top">
			<view class="flex-sub padding-left text-xl">
				可用额度：<span>{{userinfo.avaCredit}}</span>元
			</view>
		</view>
		<view class="flex p-xs mb-sm margin-top">
			<view class="flex-sub padding-left">
				<view class="text-lg">总资金</view>
				<view class="text-xl margin-top-sm">{{userinfo.allMoney}}</view>
			</view>
		</view>
		
	</view>
</template>

<script>
export default{
	data(){
		return {
			userinfo:{
				username:'ubaicai',
				avaCredit:9788.73,
				allMoney:978873
			}
		}
	}
}
</script>

<style scoped>
.mine_info {
	background-color: #373952;
}
</style>
