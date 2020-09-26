<template>
	<view class="footer-wrap">
		<view class="iconfont icon-gouwuche cart-icon"></view>
		<text>另需配送费￥5</text>
		<view class="footer-btn">
			<text>￥0起送</text>
		</view>
	</view>
</template>

<script>
</script>

<style lang="scss">
	$color3d3d3d: #3d3d3d;
	$color666: #666;
	$colorfff: #fff;
	$color999: #999;
	.footer-wrap{
		position: fixed;
		bottom: 0;
		left: 0;
		width: 100%;
		height: 100rpx;
		line-height: 100rpx;
		background-color: $color3d3d3d;
		padding: 0 30rpx;
		color: $color999;
		.cart-icon{
			display: inline-block;
			vertical-align: middle;
			font-size: 56rpx;
			width: 100rpx;
			height: 100rpx;
			line-height: 100rpx;
			border-radius: 50%;
			text-align: center;
			background-color: $color666;
			color: $colorfff;
			margin: -50rpx 20rpx 0 0;
		}
		.footer-btn{
			position: absolute;
			right: 30rpx;
			top: 50%;
			transform: translateY(-50%);
		}
	}
</style>
