<template>
	<view>
		<view class="charge-tittle">
			
					<view class="charge-tittle-text-position">
					<view class="charge-tittle-text-zhichu">
						支出
					</view>
					<view class="charge-tittle-text-shouru">
						收入
					</view>
					</view>
		<view class="charge-body">
		<view class="charge-input">
			<!-- <text>{{price}}</text> -->
			<view class="price-input">
				<input type="number" style="font-size: 40px; color: black;" placeholder="0.00"/>
			</view>
			<image src="../../static/add/st-camera@1x.png"></image>
		</view>
	
		<view class="charge-category">
			<image src="../../static/add/charge-category@1x.png"></image>
			<text>分类</text>
			<view class="charge-category-select">
				<charge-category >
				</charge-category>
			</view>
		</view>
		<view class="charge-account">
				<image src="../../static/add/charge-account@1x.png"></image>
			    <text>账户</text>
			<view class="charge-account-sort">{{accountsort}}</view>
		</view>
		<view class="charge-time">
				<image src="../../static/add/charge-time@1x.png"></image>
			    <text>日期</text>
				<view class="time-select">
					<view>{{time}}</view>
					<view>{{timeremark}}</view>
				</view>
		</view>
		<view class="charge-remark">
				<image src="../../static/add/charge-remark.png"></image>
			    <text>备注</text>
				 
		</view>
		</view>
		<view class="charge-button">
			<button>再记一笔</button>
			<button>完成</button>
		</view>
	</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				// price:'0.00',
				accountsort:'weixin',
				time:'02月01日',
				timeremark:'今天'
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss" scoped>
	.charge-tittle{
		box-sizing: border-box;
		height: 45px;
		width: 100%;
		background-color:#27424A ;
		position: relative;
		top: 0;
		padding:10px;
		.charge-tittle-text-position{
			display: flex;
			justify-content: space-around;
			@mixin charge-tittle-text {
				
			font-size: 16px;
			color: #FFFFFF;
		        &:active{
					color: #FF9502;
				}
	        }
			.charge-tittle-text-zhichu{
				@include charge-tittle-text;
			}
			.charge-tittle-text-shouru{
				@include charge-tittle-text;
			}
		}
    }
	.charge-input{
		margin-left: 20px;
		margin-right: 20px;
		margin-top: 10px;
		margin-bottom:40px ;
		display: flex;
		height: 50px;
		border-bottom:1px solid #101010;
		justify-content: space-between;
		padding: 10px;
		image{
		    width: 40px; 
			height: 40px;
			 top: 10px;
		}
	}
	@mixin charge-select($position,$number,$color) {
		margin-left: 25px;
		margin-right: 10px;
		padding: 10px 10px 10px 0;
		display: flex;
		align-items: $position;
		height: $number;
		border-bottom:$color ;
		image{
			width: 20px;
			height: 20px;
		}
		text{
			margin-left: 10px;
			font-size: 14px;
		}
	}
	.charge-category{
		@include charge-select(flex-start,150px,1px solid #BBBBBB);
		.charge-category-select{
			width: 315px;
			height: 150px;
			margin-left: 40px;
		}
	}
	.charge-account{
		@include charge-select(center,40px,1px solid #BBBBBB);
		.charge-account-sort{
			margin: 0 0 0 10px;
		}
	}
	.charge-time{
		@include charge-select(center,40px,1px solid #BBBBBB);
		.time-select{
			margin: 10px;
			display: flex;
			flex-wrap: wrap
			
		}
	}
	.charge-remark{
		@include charge-select(center,40px,0px);
	}	
	
    .charge-button{
		display: flex;
		justify-content: space-around;
		position: relative;
		top: 165px;
		button{
			width: 117px;
			height: 45px;
			border-radius: 23px;
			background-color: #2c4a53 ;
			font-size: 16px;
			color: #FDFEFE;
			&:active{
				background-color: #568EA0 ;
				color: #27424A;
			}
		}
	}
</style>
