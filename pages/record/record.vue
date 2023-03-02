<template>
	<view>
		<view class="row_block">
			<view class="the_title" style="justify-content: space-between;">
				<view class="left_title">
					<view class="title_icon"></view>
					<text class="margin_stand-samll font-big wide">历史趋势</text>
				</view>
				<view class="right_btn">
					<view v-for="(item,index) in historyBtn" :key="index" :class="item.state ? 'active_btn':''"
						@click="changeHistoryBtn(item.type)">{{item.name}}</view>
				</view>
			</view>
			<view class="charts-box" style="height: 200px;">
				<qiun-data-charts type="line" canvasId="finance_a" :canvas2d="isCanvas2d" :resshow="delayload"
					:opts="{xAxis:{itemCount:12,disableGrid:true},yAxis:{disableGrid:true,data:[{disabled:true}]}}"
					:chartData="historyData" />
			</view>
		</view>
	</view>
</template>

<script>
	import dataOne from '../../static/json/finance/1.json';
	import expendDetail from '../../static/json/finance/2.json';
	
	export default {
		data() {
			return {
				info: this.$store.state.userInfo, //用户数据
				scrollHeight: "600px", //数据展示体高度
				isCanvas2d: this.$Config.ISCANVAS2D,
				historyData: {},
				dataOne,
				expendDetail,
				expendCount:0,
				delayload: false,
				
				historyBtn: [{
						name: "支出",
						state: 1,
						type: "expend"
					},
					{
						name: "收入",
						state: 0,
						type: "income"
					},
					{
						name: "结余",
						state: 0,
						type: "remaining"
					},
				],
			}
		},
		watch: {
			"historyBtn": {
				deep: true,
				handler: function(newVal, oldVal) {
					this.filterHistoryData();
				}
			}
		},
		methods: {
				changeHistoryBtn(type) {
					for (let i = 0; i < this.historyBtn.length; i++) {
						if (this.historyBtn[i].type == type) {
							this.historyBtn[i].state = 1
						} else {
							this.historyBtn[i].state = 0
						}
					}
				},
				filterHistoryData() {
					let type = this.historyBtn.filter(x => x.state == 1)[0].type;
					switch (type) {
						case "expend":
							this.historyData = this.dataOne.expend;
							break;
						case "income":
							this.historyData = this.dataOne.income;
							break;
						case "remaining":
							this.historyData = this.dataOne.remaining;
							break;
					}
				},
		}
	}
</script>

<style lang="scss" scoped>
	.body {
		height: 100%;
		background-color: #560594;
		margin: 0;
		padding-bottom: 20rpx;
		li{
			list-style-type: none;
		}
		.main {
			width: 100%;
			padding: 0 10rpx;
			box-sizing: border-box;
			margin-top: 20rpx;
			
			.row_block {
				width: 100%;
				box-sizing: border-box;
				background-color: #fff;
				border-radius: 12rpx;
				position: relative;
				padding: 20rpx;
			
				&::after {
					content: "";
					height: 0px;
					width: 92%;
					position: absolute;
					transform: translateX(-50%);
					left: 50%;
					bottom: 0;
					border-top: 1px dashed #ccc;
				}
			}
			    .the_title {
			    	display: flex;
			    	align-items: center;
			    
			    	.left_title {
			    		display: flex;
			    		align-items: center;
			    	}
			    
			    	.title_icon {
			    		background-color: #7E7E7E;
			    		height: 40rpx;
			    		width: 10rpx;
			    		border-radius: 10rpx;
			    		margin-right: 20rpx;
			    		font-size: 16px;
			    		font-weight: 600;
			    	}
			    }
		}
}

</style>
