<template>
    <view class="switch-wrap">
            <view class="active">点菜</view>
            <view>评价</view>
            <view>商家</view>
    </view>
</template>

<script>
export default {
    data() {
        return {}
    }
}
</script>

<style>
    .switch-wrap{
        padding: 30rpx 15rpx 0;
        border-bottom: 1px solid #f0f1f4;
		background-color: #fff;
    }
    .switch-wrap view{
        display: inline-block;
        vertical-align: top;
        width: 240rpx;
        height: 60rpx;
        text-align: center;
        color: #5a6586;
    }
    .switch-wrap view.active{
        position: relative;
        font-weight: bold;
        font-size: 32rpx;
        color: #313651;
    }
    .switch-wrap view.active::after{
        content: "";
        position: absolute;
        left: 50%;
        bottom: 0;
        transform: translateX(-50%);
        width: 50rpx;
        height: 2px;
        background-color: #FFD369;
    }
</style>
