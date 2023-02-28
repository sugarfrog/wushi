<template>
	<view>
		<view class="bill-list">
			<view class="bill-positon">
				<view class="bill-box">
					 <list>
					    <!-- 注意事项: 不能使用 index 作为 key 的唯一标识 -->
					    <cell v-for="(item, index) in dataList" :key="item.id">
					      <text>{{item.name}}</text>
					    </cell>
					  </list>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				 dataList: [{id: "1", name: 'A'}, {id: "2", name: 'B'}, {id: "3", name: 'C'}]
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss" scoped>
	.bill-list{
		.bill-positon{
			position: relative;
			left: 0px;
			top: 25px;
			// padding: 70px 0;
			
			.bill-box{
				width:100%;
				height: 600px;
				border-radius: 27px 27px 0 0;
				background-color: #F7F7F7;
		}
	}
}
</style>
