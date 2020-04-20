<template>
	<view>
		<!-- 我的信息 -->
		<mine-info></mine-info>
		<!-- 菜单列表 -->
		<view class="cu-list menu sm-border">
			<view class="cu-item arrow" style="background-color:black;border-bottom:3upx solid #999"
				v-for="item in iconList">
				<view class="content  theme_center row_center">
					<text :class="[item.iconColor,item.icon]"
					style="font-size:50upx"></text>
					<text class="margin-left-xs text-lg">{{item.name}}</text>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
import mineInfo from '../../components/mineInfo.vue';
export default {
	components:{
		mineInfo
	},
	data(){
		return {
			iconList:[
				{ name:'银行转账',iconColor:'text-red',icon:'cuIcon-refund' },
				{ name:'提现',iconColor:'text-orange',icon:'cuIcon-redpacket' },
				{ name:'实名认证',iconColor:'text-blue',icon:'cuIcon-profile' },
				{ name:'修改密码',iconColor:'text-blue',icon:'cuIcon-lock' },
				{ name:'交易记录',iconColor:'text-yellow',icon:'cuIcon-text' },
				{ name:'我的自选',iconColor:'text-green',icon:'cuIcon-edit' },
				{ name:'安全退出',iconColor:'text-purple',icon:'cuIcon-icloading' }
			]
		}
	}
}
</script>

<style>
</style>
