<template>
	<view class="mall-list">
		<view  class="mall-box" v-for="(mall,index) in mall_list" :key="index" @click="mall_detail">
			<view class="mall-cover" :style="{'background-image': 'url('+mall.image+')'}">
				<text>外卖 · 30分钟送达</text>
			</view>
			<view class="mall-title">{{ mall.title }}</view>
			<view class="mall-score">
				<text>4.7分</text>
				<text>每次味道都很棒，味道很好</text>
			</view>
			<div class="mall-reduct">
				<div>30减17</div>
				<div>30减17</div>
				<div>30减17</div>
			</div>
			<div class="mall-price">人均 ￥18  |  月售 8147</div>
		</view>
		<view class="mall-more">没有更多内容</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				mall_list: [{
					image: "//img14.360buyimg.com/n7/jfs/t1/97161/40/12127/66234/5e440190E7cd0f54e/33627b2c39a67241.jpg",
					title: "限时赠送30天无忧体验服务，尊享白条分期24期免息，骁龙865处理器【小米10至尊版限时预约中!点击直达】",
					price: "3999.00"
				},{
					image: "//img14.360buyimg.com/n7/jfs/t1/97161/40/12127/66234/5e440190E7cd0f54e/33627b2c39a67241.jpg",
					title: "限时赠送30天无忧体验",
					price: "3999.00"
				},{
					image: "//img14.360buyimg.com/n7/jfs/t1/97161/40/12127/66234/5e440190E7cd0f54e/33627b2c39a67241.jpg",
					title: "限时赠送30天无忧体验服务，尊享白条分期24期免息，骁龙865处理器【小米10至尊版限时预约中!点击直达】",
					price: "3999.00"
				},{
					image: "//img14.360buyimg.com/n7/jfs/t1/97161/40/12127/66234/5e440190E7cd0f54e/33627b2c39a67241.jpg",
					title: "限时赠送30天无忧体验服务，尊享白条分期24期免息，骁龙865处理器【小米10至尊版限时预约中!点击直达】",
					price: "3999.00"
				}]
			}
		},
		methods: {
			mall_detail: function() {
				uni.navigateTo({
				    url: '/pages/detail/index'
				});
			}
		}
	}
</script>

<style lang="scss">
	.mall-list {
		padding: 0 20rpx 120rpx;
		.mall-box{
			display: inline-block;
			vertical-align: top;
			width: 345rpx;
			&:nth-child(2n){
				margin-left: 20rpx;
			}
			background-color: #ffffff;
			border-radius: 10rpx;
			margin-top: 20rpx;
			overflow: hidden;
			.mall-cover{
				position: relative;
				width: 100%;
				height: 200rpx;
				display: inline-block;
				vertical-align: top;
				background: {
					size: cover;
					position: center;
				}
				&>text{
					position: absolute;
					bottom: 5px;
					left: 10px;
					padding: 1px 10rpx;
					background-color: rgba(136, 145, 171, 0.5);
					font-size: 20rpx;
					color: #fff;
					border-radius: 5rpx;
				}
			}
		}
		// 子嵌套夫,样式会被影响？？
		.mall-title{
			font-size: 28rpx;
			line-height: 40rpx;
			margin: 20rpx;
			display: -webkit-box;
			-webkit-line-clamp:2;
			overflow: hidden;
			text-overflow: ellipsis;
			-webkit-box-orient: vertical;
		}
		.mall-score{
			font-size: 20rpx;
			padding: 0 20rpx;
			&:first-child{
				color: #fe587a;
			}
			&:last-child{
				color: #8891ab;
				margin-left: 12rpx;
			}
		}
		.mall-reduct{
			padding: 10rpx 20rpx;
			&>div:first-child{
				margin-left: 0;
			}
			&>div{
				display: inline-block;
				vertical-align: top;
				font-size: 18rpx;
				color: #fe587a;
				padding: 0 10rpx;
				border-radius: 5rpx;
				border: 1px solid #fe587a;
				background-color: rgba(254, 88, 122, 0.1);
				margin-left: 5rpx;
			}
		}
		.mall-price{
			font-size: 20rpx;
			color: #8891ab;
			padding: 0 20rpx 20rpx;
		}
		.mall-more{
			font-size: 24rpx;
			color: #8891ab;
			height: 120rpx;
			line-height: 120rpx;
			text-align: center;
		}
	}
</style>
