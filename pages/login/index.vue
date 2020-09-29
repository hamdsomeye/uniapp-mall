<template>
	<view class="login">
		<view class="login-logo"></view>
		<button type="primary" open-type="getUserInfo" @getuserinfo="getuserinfo">微信用户一键登录</button>
		<view class="phone-login">手机号码登录/注册</view>
	</view>
</template>

<script>
	export default {
		methods: {
			getuserinfo(e){
				console.log(e)
			}
		}
	}
</script>

<style lang="scss">
	page{
		background-color: #fff;
		.login{
			padding: 0 100rpx;
			.login-logo{
				width: 140rpx;
				height: 140rpx;
				background-image: url(@/static/logo.png);
				background-position: center;
				background-size: cover;
				margin: 260rpx auto 200rpx;
			}
			.phone-login{
				text-align: center;
				padding: 40rpx;
				color: #5A6586;
			}
		}
	}
</style>
