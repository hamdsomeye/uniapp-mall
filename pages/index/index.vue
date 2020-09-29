<template>
	<view class="content">
		<div class="content-top"></div>
		<view class="header" @click="login">
			<icon class="user-headimg iconfont icon-morentouxiang"></icon>
			<view class="user-name">请先登录</view>
		</view>
		<view class="content-box">
			<view class="content-coupon item-btn-touch">
				<icon class="iconfont icon-youhuiquan"></icon>
				<div>优惠券</div>
			</view>
			<view class="content-member item-btn-touch">
				<icon class="iconfont icon-huiyuanzhongxin"></icon>
				<div>会员中心</div>
			</view>
			<view class="content-merchant item-btn-touch">
				<icon class="iconfont icon-shanghuzhinan"></icon>
				<div>商户中心</div>
			</view>
			<view class="content-order item-btn-touch">
				<icon class="iconfont icon-wodedingdan"></icon>
				<div>全部订单</div>
			</view>
		</view>
		<view class="footer">
			<view class="footer-feedback item-btn-touch">
				<view>意见反馈</view>
				<icon class="iconfont icon-arrow-right"></icon>
			</view>
			<view class="footer-setting item-btn-touch">
				<view>个人设置</view>
				<icon class="iconfont icon-arrow-right"></icon>
			</view>
			<view class="footer-customer item-btn-touch">
				<view>联系客服</view>
				<icon class="iconfont icon-arrow-right"></icon>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {
			
		},
		methods: {
			login() {
				uni.navigateTo({
					url:  '/pages/login/index'
				})
			}
		}
	}
</script>

<style lang="scss">
	page{
		background-color: #fff;
		.content-top{
			height: 20rpx;
			background-color: #f7f7f9;
		}
		.header{
			width: 100%;
			height: 350rpx;
			background-color: #fff;
			margin-top: 20rpx;
			padding: 50rpx 0;
			.user-headimg{
				font-size: 150rpx;
				display: flex;
				justify-content: center;
			}
			.user-name{
				text-align: center;
			}
		}
		.content-box{
			margin: -50rpx 30rpx 0;
			box-shadow: 0 1px 6px rgba(0,0,0,.117647);
			border-radius: 10rpx;
			overflow: hidden;
			&>view{
				display: inline-block;
				vertical-align: top;
				width: 25%;
				height: 160rpx;
				text-align: center;
				background-color: #fff;
				&>icon{
					font-size: 32rpx;
					padding: 25rpx 0 10rpx;
				}
			}
			.content-coupon{
				&>icon{
					color: #FE587A;
				}
			}
			.content-member{
				&>icon{
					color: #F0AD4E;
				}
			}
			.content-merchant{
				&>icon{
					color: #1a82fc;
				}
			}
		}
		.footer{
			margin: 30rpx 30rpx 0;
			box-shadow: 0 1px 6px rgba(0,0,0,.117647);
			&>view{
				position: relative;
				height: 100rpx;
				line-height: 100rpx;
				padding: 0 30rpx;
				&::after{
					content: '';
					position: absolute;
					bottom: 0;
					left: 0;
					width: 100%;
					height: 1px;
					background-color: #f0f1f4;
				}
				&>icon{
					position: absolute;
					right: 30rpx;
					top: 50%;
					transform: translateY(-50%);
					color: #c3c8d5;
				}
			}
		}
	}
</style>
