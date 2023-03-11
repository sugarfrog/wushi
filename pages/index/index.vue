<template>
	<view>
		
		<view>
		<navbar></navbar>	
		</view>
		
		<view class="chart-position">
		<card-chart>
		</card-chart>
	</view>
	
	<view class="bill-list-body">
		<view class="bill-list-head">
			<view class="bill-list-head-text">
				<view>
					最近交易
				</view>
				<view >
				菜单
			    </view>
			</view>
		</view>
		<bill-list ></bill-list>
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
	.chart-position{
		display: flex;
		position: relative;
		// background-color: #101010;
		padding: 20px;
		justify-content: center;
		top: 82px;
	}
	.bill-list-body{
		position:relative;
		top: 120px;
		height: 999px; 
		border-radius: 27px 27px 0 0;
		padding: 20px;
		background-color: #ffffff;
		.bill-list-head{
			width: 100%;
			height: 20px;
			.bill-list-head-text{
				font-size: 14px;
			    color: #101010 ;
			    display: flex;
				justify-content:space-between;
			}
		}
	}
	
	
</style>