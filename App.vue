<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	@import "colorui/main.css";
	@import "colorui/icon.css";
	page{
		background-color: #000;
		color:#fff;
	}
	.theme_bg {
		background-color: #000!important;
	}
	.theme_color {
		color:#fff!important;
	}
	.theme_center {
		display: flex;
	}
	.row_center {
		align-items: center;
	}
	.column_center {
		justify-content: center;
	}
</style>
