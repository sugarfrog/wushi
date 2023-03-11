<script>	
	export default {
		created() {
			// #ifdef APP-PLUS
			plus.navigator.closeSplashscreen(); 
			// #endif 
		},
		onLaunch: function() {
			console.log('App Launch')
			//自定义导航栏
			uni.getSystemInfo({
				success: function(e) {
					// #ifndef MP
					Vue.prototype.StatusBar = e.statusBarHeight;
					if (e.platform == 'android') {
						Vue.prototype.CustomBar = e.statusBarHeight + 50;
					} else {
						Vue.prototype.CustomBar = e.statusBarHeight + 45;
					};
					// #endif
					
					// #ifdef MP-WEIXIN
					Vue.prototype.StatusBar = e.statusBarHeight;
					let custom = wx.getMenuButtonBoundingClientRect();
					Vue.prototype.Custom = custom;
					Vue.prototype.CustomBar = custom.bottom + custom.top - e.statusBarHeight;
					// #endif		
					
					// #ifdef MP-ALIPAY
					Vue.prototype.StatusBar = e.statusBarHeight;
					Vue.prototype.CustomBar = e.statusBarHeight + e.titleBarHeight;
					// #endif
				}
			})
			//tabbar中间按钮跳转
			uni.onTabBarMidButtonTap((e) => {
				let _this = this
				// #ifdef APP-PLUS
				// 通过 id 获取 nvue 子窗体  
				const subNVue = uni.getSubNVueById('select')
				// 打开 nvue 子窗体  
				subNVue.show('none', 300, function() {
					// 打开后进行一些操作...  
					// 在 subNVue/vue 页面触发事件  
					// $emit(eventName, data) 
					uni.$emit('release', {
						// detailId: data.id,
						// detailUserId: data.userId,
						// commentCount: data.commentCount
					});
					subNVue.setStyle({
						left:'100px',
					})
				});
				// #endif
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
	page{
		background-color: #f8f8f9;
	}
	/*每个页面公共css */
</style>
