<template>
	<view>
		<view>
		<navbar></navbar>	
		</view>
		<view class="card-chart">
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
	<view >
		

	<!-- <uni-list >
			    <uni-list-item title="列表文字" note="列表描述信息" rightText="-100.00" @click="change"></uni-list-item>
			    <uni-list-item :disabled="true" title="列表文字" note="列表禁用状态"></uni-list-item>
	</uni-list> -->
	</view>
	</view>
</template>

<script>
	// 通过 id 获取 nvue 子窗体  
	const subNVue = uni.getSubNVueById('select')  
	// 打开 nvue 子窗体  
	subNVue.show('slide-in-left', 300, function(){  
	    // 打开后进行一些操作...  
	    //   
	});  
	// 关闭 nvue 子窗体  
	subNVue.hide('fade-out', 300)
	
	export default {
		data() {
			return {
		
		 	}
		 },
		onLoad(){

		},
		methods: {
			// change(){
			// 	console.log("成功")
			// 	uni.navigateTo({
			// 		url:"/pages/charge/charge"
			// 	})
			// }

		}
	}
</script>

<style lang="scss" scoped>
	.card-chart{
		position: relative;
		left: 5px;
		top: 10px;
	}
	.bill-list-body{
		width:100%;
		height: 999px;
		border-radius: 27px 27px 0 0;
		background-color: #F7F7F7;
		.bill-list-head{
			width: 100%;
			height: 40px;
			.bill-list-head-text{
				margin: 20px;
				font-size: 14px;
			    color: #101010 ;
			    display: flex;
				position: relative;
				top: 10px;
				justify-content:space-between;
			}
		}
	}
	
	
</style>