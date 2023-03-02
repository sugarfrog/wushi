<template>
	<view>
		<view class="charge-tittle">
			<view class="charge-tittle-text">
				<view hover-class="charge-tittle-text-hover">
					<text>支出</text>
					<text>收入</text>
				</view>
			</view>
		</view>
		<view>
			<text>{{price}}</text>
		</view>
		<view class="line"></view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				prrice:'0.00'
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss" scoped>
	.charge-tittle{
		height: 67px;
		width: 100%;
		background-color:#27424A ;
		position: relative;
		top: 0px;
		.charge-tittle-text{
			display: flex;
			font-size: 36px;
			color: #FFFFFF;
		}
		.charge-tittle-text-hover{
			display: flex;
			color: #FF9502;
		}
	}
	.line{
		width: 356px;
		height: 1px;
		border: 1px solid rgba(16, 16, 16, 1);
		color:#101010 ;
	}
	
</style>
