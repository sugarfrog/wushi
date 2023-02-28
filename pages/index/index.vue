<template>
	<view>
		<view>
		<navbar></navbar>	
		</view>
		<view class="card-chart">
		<card-chart></card-chart>
	</view>
	<view>
		<bill-list></bill-list>
	</view>
	</view>
	
	
	
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style lang="scss" scoped>
	.card-chart{
		position: relative;
		left: 5px;
		top: 10px;
	}
	.bill-list{
		position: relative;
		top: 20px;
	}
	
</style>