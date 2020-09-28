<template>
	<view class="goods-type-model" v-if="showModel">
		<view class="model-bg" @click="hiddenModel()"></view>
		<view class="model-content">
			<view class="model-title">规格</view>
			<view class="model-btn">确定</view>
			<view class="model-info">
				<view v-for="(type,index) in goodsType" :key="index" :class="(select_type == type.id ? 'active':'')" @click="selectType(type.id)">
					{{type.name}}
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default{
		props: {
			show: {
				type: Boolean,
				default: false
			},
			goodsType: {
				type: Array,
				default: []
			}
		},
		data() {
			return {
				select_type: 1,
				showModel: false
			}
		},
		watch: {
			show: function(e){
				this.showModel = e
			}
		},
		methods: {
			selectType: function(type_id) {
				this.select_type  =  type_id
			},
			hiddenModel: function() {
				this.showModel = false
				this.$emit('hiddenModel',false)
			}
		}
	}
</script>

<style lang="scss">
	.goods-type-model{
		.model-bg{
			position: absolute;
			top: 0;
			bottom: 0;
			left: 0;
			width: 100%;
			background-color: rgba(8, 17, 41, 0.5);
		}
		.model-content{
			position: absolute;
			bottom: 0;
			left: 0;
			width: 100%;
			height: 600rpx;
			border-radius: 20rpx 20rpx 0 0;
			background-color: #fff;
			.model-title{
				height: 100rpx;
				line-height: 100rpx;
				padding: 0 30rpx;
			}
			.model-btn{
				position: absolute;
				right: 30rpx;
				top: 20rpx;
				font-size: 28rpx;
				color: #fff;
				width: 120rpx;
				height: 60rpx;
				line-height: 60rpx;
				text-align: center;
				background-color: #F0AD4E;
				border-radius: 30rpx;
				color: #333;
			}
			.model-info{
				padding: 0 10rpx;
				&>view{
					padding: 20rpx;
					border: 1px solid #e1e3ea;
					display: inline-block;
					vertical-align: top;
					line-height: 28rpx;
					margin-left: 20rpx;
					margin-top: 20rpx;
					border-radius: 8rpx;
				}
				&>view.active{
					color:#F0AD4E;
					background-color: rgba(255, 233, 180, 0.2);
					border: 1px solid #F0AD4E;
				}
			}
		}
	}
</style>
