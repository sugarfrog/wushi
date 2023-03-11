<template>
	<view>
		<view class="category">
				<view class="category-text" v-for="item in categoryList">
				{{item.name}}
			</view>
			
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				categoryList:[{name:"工资"},
				{name:"工资"},
				{name:"工资"},
				{name:"工资"},
				{name:"工资"},
				{name:"工资"},
				{name:"工资"}]
		}
		},
		methods: {
			
		}
	}
</script>

<style  lang="scss" scoped>
	.category{
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;
		padding: 0px 10px 10px 10px;
		.category-text{
			margin-bottom: 20px;
			width: 72px;
		    height: 24px;
		    border-radius: 20px;
		    border: 2px solid rgba(86, 142, 160, 1);
			color: rgba(112, 182, 205, 1);
			font-size: 14px;
			text-align: center;
		}
	}

</style>
