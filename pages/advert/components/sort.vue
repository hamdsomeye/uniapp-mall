<template>
	<u-sticky :fixed="sticky">
		<view class="mall-sort">
			<view class="mall-sort-box item-btn-touch">
				<view class="iconfont icon-shangcheng color-1a82fc"></view>
				<text class="item-btn-touch">外卖</text>
			</view>
			<view class="mall-sort-box item-btn-touch">
				<view class="iconfont icon-daifukuan-2 color-f6c6ce"></view>
				<text class="item-btn-touch">美食</text>
			</view>
			<view class="mall-sort-box item-btn-touch">
				<view class="iconfont icon-shouhou color-fe587a"></view>
				<text class="item-btn-touch">特价</text>
			</view>
			<view class="mall-sort-box item-btn-touch">
				<view class="iconfont icon-fufei color-528ce0"></view>
				<text class="item-btn-touch">优惠券</text>
			</view>
		</view>
	</u-sticky>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		}
	}
</script>

<style lang="scss">
	.mall-sort{
		font-size: 0;
		padding: 0 30rpx 20rpx;
		background-color: #fff;
		.mall-sort-box{
			display: inline-block;
			vertical-align: top;
			width: 25%;
			text-align: center;
			padding: 20rpx 0;
			&>view{
				padding-bottom: 2rpx;
				font-size: 48rpx;
			}
			&>text{
				font-size: 28rpx;
			}
		}
	}
</style>
