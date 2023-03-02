<template>
	<view class="mask" @click="dimiss">
		<view class="content">
			
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
		    //点击mask消失，由于是页面实际相当于返回
			dimiss(){
				uni.navigateBack({
					delta: 1
				})
			}
		}
	}
</script>

<style>
page {
	width: 100%;
	height: 100%;
	background: rgba(0,0,0,0.4);
}
.mask {
		width: 100%;
		height: 100%;
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
	}
.content {
	width: 200rpx;
	height: 200rpx;
	border-radius: 20rpx;
	background-color: white;
}
</style>

