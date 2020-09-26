<template>
    <view class="header-wrap">
        <view class="merchant-image" style="background-image: url(https://img.meituan.net/msmerchant/af6e5f77dca691d39e1583847349f1d0511132.jpg@220w_125h_1e_1c)"></view>
        <view class="merchant-info">
            <text>阿强家酸菜鱼（石牌店）</text>
            <view>60分钟｜18.3k</view>
            <view　class="reduct-info">
                <view>减</view>
                <view>配送费立减３元</view>
            </view>
        </view>
    </view>
</template>

<script>
export default{

}
</script>

<style lang="scss">
    .header-wrap{
        background-color: #2f2f3b;
        width: 100%;
        height: 200rpx;
		.merchant-image{
		    display: inline-block;
		    vertical-align: top;
		    background-image: url("https: //img.meituan.net/msmerchant/af6e5f77dca691d39e1583847349f1d0511132.jpg@220w_125h_1e_1c");
		    width: 150rpx;
		    height: 150rpx;
		    background-size: cover;
		    background-position: center;
		    margin: 30rpx;
		    border-radius: 5rpx;
		}
		.merchant-info{
		    display: inline-block;
		    font-size: 26rpx;
		    color: #fff;
		    margin-top: 40rpx;
			.reduct-info{
			    display: inline-block;
			    vertical-align: top;
			    margin-top: 16rpx;
			}
			.reduct-info view:first-child{
			    display: inline-block;
			    vertical-align: top;
			    background-color: #fe587a;
			    color: #fff;
			    width: 25rpx;
			    text-align: center;
			    font-size: 20rpx;
			    border-radius: 5rpx;
			}
			.reduct-info view:last-child{
			    display: inline-block;
			    vertical-align: top;
			    color: #fff;
			    margin-left: 16rpx;
			    line-height: 30rpx;
			}
		}
    }
</style>
