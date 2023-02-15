<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
			//tabbar中间按钮跳转
			uni.onTabBarMidButtonTap(()=>{
				uni.navigateTo({
					url:"../rili/rili",
					animationType:"slide-in-bottom"
				})
			})
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
	/*每个页面公共css */
</style>
