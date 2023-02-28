<template>
	<view class="navbar" >
		<view class="navbar-fixed">
			<!-- 状态栏 -->
			<view :style="{height:statusBarHeight + 'px'}"></view>
			<view class="navbar-content" >
							<view class="navbar-search">
								<view class="navbar-search_icon">
									<uni-icons type="search" size="16" color="#999">
										<view class="navbar-search_text">
										<input  type="text" placeholder="搜索"  />	
										</view>
									</uni-icons>
								</view>
							</view>
							<view>
								<view style="display: flex; position:relative; left: 140px;">
									<image  style="height:42px ; width: 42px;  top: 0px;"src="../../static/add/account.png"></image>
								</view>
								<view style="display: flex; position:relative;top: 1px; left: 140px;">
									<text style="font-size: 10px; color: aliceblue;">神奇洋辰</text>
								</view>
							</view>
							<view>
								<view style="display: flex; position:fixed; left: 23px;">
									<image style="height:42px ; width: 42px;  top: 0px;" src="../../static/add/bill-book.png"></image>
								</view>
								<view style="display: flex; position:fixed;top: 86px; left: 23px;">
									<text style="font-size: 10px; color: aliceblue;">家庭账本</text>
								</view>
							</view>
							</view>
							
						</view>
					</view>
</template>

<script>
	export default {
			data() {
				return {
					statusBarHeight: 20,
				};
			},
			mounted() {
						let that = this;
						//通过uni自带api获取手机系统信息
						uni.getSystemInfo({
							success: function(res) {
								// console.log(res)
								that.statusBarHeight = res.statusBarHeight; //手机状态栏高度
								let isiOS = res.system.indexOf('iOS') > -1; //是否为iOS系统
								that.barHeight = !isiOS ? 48 : 44; //导航栏高度，iOS：48，Android：44
								that.barWidth = res.windowWidth - 87; //nabbar可操作宽度 = 屏幕宽度 - 小程序右上角的胶囊宽度（87）
							}
						})
			},
			methods: {}
		}
</script>

<style lang="scss" scoped>
	.navbar{
		.navbar-fixed{
			position: fixed;
			top: 0;
			left: 0;
			z-index: 99;
			width: 100%;
			background-color: #27424a;
			
			.navbar-content{
				padding: 5px;
				// box-sizing: border-box;
				display: flex;
				// justify-content: center;
				// align-items: center;
				height: 52px;

				.navbar-search{
					display: flex;
				    // align-items: center;
					position: relative;
					background-color: white;
					left: 100px;
					top: 13px;
					width: 200px;
					height: 30px;
					border-radius: 15px;
					text-align: left;
					
					.navbar-search_iocn{
						margin-right: 10px;
						display: flex;
					}
					.navbar-search_text{
						// width: 100%;
						font-size: 14px;
						color: #999;
						left: 10px;
						text-align: center;
					}
					
				}
				.navbar-acount{
					left: 100px;
					top: 44px;
					// line-height: 20px;
					// background-color: rgba(79, 79, 79, 1);
					text-align: center;
					// border: 1px solid rgba(255, 255, 255, 1);
					.navbar-account-img{
						width: 10px;
						height: 10px;
						// border-radius:50%; 
						// overflow:hidden;
					}
				}
			}
			
		}
		
	}
</style>
