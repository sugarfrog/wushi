<template>
	<view class="card-chart">
			<view class="chart-box">
				<view class="card-chart-text-mouth">
					<text>2月</text>
					<text style="color:#FF8282 ;position:relative;left: 46px;">支出</text>
					<image style="position: relative;left: 70px;width: 24px;height: 24px;top: 5px;" src="../../static/card-chart-icon.png"></image>
					<text style="position: relative;left: 75px;color: #FF5B5B ;">243</text>
				</view>
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
			
		}
	}
</script>

<style lang="scss" scoped>
	.card-chart{
			.chart-box{
				width: 400px;
				height: 164px;
				border-radius: 27px;
				background-color: #ffffff;
				.card-chart-text-mouth{
					position: relative;
					color: #70B6CD;
					font-size: 14px;
					top:0px;
					left:30px;
				}
				
			}
		}
		

</style>
