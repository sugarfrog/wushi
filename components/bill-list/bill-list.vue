<template>
	<view>
		<view class="bill-list">
				<view class="bill-list-item"  v-for="bill in billList">
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
					
					
						<!-- <list> -->
					    <!-- 注意事项: 不能使用 index 作为 key 的唯一标识 -->
					    <!-- <cell v-for="(item, index) in dataList" :key="item.id">
					      <text style="font-size: 10px;">{{item.name}} </text>
						  <text style="font-size: 8px; top: 12px; text-align: left;">{{item.massage}}</text>
						  <text style="font-size: 10px; left: 400px; color: red;">{{item.price}}</text>
					    </cell>
					  </list> -->
					 
				</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				 billList: [{name: "午饭", time: "02/01",type:"饮食",price:"-100.00"},
				 {name: "午饭", time: "02/01",type:"饮食",price:"-100.00"},
				 {name: "午饭", time: "02/01",type:"饮食",price:"-100.00"},
				 {name: "午饭", time: "02/01",type:"饮食",price:"-100.00"},
				 {name: "午饭", time: "02/01",type:"饮食",price:"-100.00"},
				 {name: "午饭", time: "02/01",type:"饮食",price:"-100.00"},
				 {name: "午饭", time: "02/01",type:"饮食",price:"-100.00"},
				 {name: "午饭", time: "02/01",type:"饮食",price:"-100.00"},
				 {name: "午饭", time: "02/01",type:"饮食",price:"-100.00"},
				 {name: "午饭", time: "02/01",type:"饮食",price:"-100.00"},
				 {name: "午饭", time: "02/01",type:"饮食",price:"-100.00"},
				 ]
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss" scoped>
	.bill-list{
		width: 90%;
		height: 45px;
		border-bottom: 2px #F7F7F7 ;
		margin: 20px;
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
