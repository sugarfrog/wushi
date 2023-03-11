<template>
	<view>
		<view class="bill-list">
				<view class="bill-list-item"  v-for="bill in localData">
					<!-- <image></image> -->
					
						<view class="bill-list-name">
						{{bill.name}}
						<view class="bill-list-time">
						{{bill.time}}
						</view>
					    </view>
						<view class="bill-list-type">
						{{bill.type}}
						</view>
						<view class="bill-list-price">
						{{bill.price}}
						</view>
				</view>
		</view>
	</view>
</template>

<script>
	const billList = require('@/static/json/billList.json')
	export default {
		data() {
			return {
				localData:billList
			}
		},
		onLoad() {
			console.log('billJson'+JSON.stringify(billList));
		},
		methods: {
		}
	}
</script>

<style lang="scss" scoped>
	.bill-list{
		height: 45px;
		border-bottom: 2px #ebebeb ;
		// margin: 20px;
		.bill-list-item{
			display: flex;
			justify-content: space-between;
			margin-top: 40px;
			margin-bottom: 40px;
			.bill-list-name{
				color: #949494 ;
				font-size: 13px;
				.bill-list-time{
					color: #B0B0B0 ;
					font-size: 12px;
				}
			}
			.bill-list-type{
				color:#949494 ;
				font-size: 13px;
			}
			.bill-list-price{
				color: #101010 ;
				font-size: 14px;
			}
		}
}
</style>
