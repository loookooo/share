<template>
	<view class="cu-bar" style="background-color: #1E2227;">
		<view class="action">
			<text class="cuIcon-titles text-red"></text>
			<text class="text-lg">{{title}}</text>
		</view>
	</view>
</template>

<script>
export default {
	props:{
		title:{
			type:String,
			require:true
		}
	}
}
</script>
