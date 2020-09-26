<template>
    <view class="goods-wrap">
        <scroll-view  class="goods-left" scroll-y :style="{height: goodsHeight+'px'}">
            <view class="goods-left-box">
                <view v-for="(data,index) in label.rows" :key="index" :class="select_label == data.id ? 'active':''" @click="switchLabel(data.id)">{{data.name}}</view>
            </view>
        </scroll-view>
        <scroll-view class="goods-right" scroll-y :scroll-into-view="into_view"  scroll-with-animation @scroll="goodScroll" :style="{height: goodsHeight+'px'}">
            <view class="goods-right-box">
                <view class="goods-list" v-for="(data,index) in list.rows" :key="index" :id="'goods'+data.id">
                    <view class="goods-info-image" :style="{'background-image': 'url('+data.headimg+')'}"></view>
                    <view class="goods-info-box">
                        <view class="goods-info-name">{{data.title}}</view>
                        <view class="goods-info-num">月售{{data.month_sales}}+ 赞{{data.praise}}</view>
                        <view class="goods-info-price-box">
                            <text class="goods-info-price">¥ {{data.real_price}}</text>
                            <text class="goods-info-tip">/1人份</text>
                            <text class="goods-info-original">¥ {{data.past_price}}</text>
                        </view>
                    </view>
                     <view class="select-type" @click="goodsTypeInfoModel(data.id)">选规格</view>
                </view>
            </view>
        </scroll-view>
    </view>
</template>

<script>
export default {
    data() {
        return {
            height: 0,
            screenHeight: 0,
			into_view: '',
			select_label: 1,
			topList: [],
			leftClick: false,
			label: {
				rows: [
						{id:1,name: '热销'},
						{id:2,name: '折扣'},
						{id:3,name: '特价'},
						{id:4,name: '限时抢购'},
						{id:5,name: '必选'},
						{id:6,name: '小吃'},
						{id:7,name: '加饭'},
						{id:8,name: '饮料'},
						{id:9,name: '新品上线'},
						{id:10,name: '套餐'}
					]
			},
			list: {
				rows: [{
					id: 1,
					headimg: 'https://img.meituan.net/msmerchant/af6e5f77dca691d39e1583847349f1d0511132.jpg',
					title: '虫草花汤',
					month_sales: '600',
					praise: '33',
					real_price: '2.49',
					past_price: '5',
					goods_type_info: [{
						'id': 1,
						'goods_id': 1,
						'name': '虫汤 600ml+2元'
					},{
						'id': 2,
						'goods_id': 1,
						'name': '草汤 600ml+2元'
					},{
						'id': 3,
						'goods_id': 1,
						'name': '花汤 600ml+2元'
					}]
				},{
					id: 2,
					headimg: 'https://img.meituan.net/msmerchant/af6e5f77dca691d39e1583847349f1d0511132.jpg',
					title: '虫草花汤',
					month_sales: '600',
					praise: '33',
					real_price: '2.49',
					past_price: '5',
					goods_type_info: [{
						'id': 1,
						'name': '虫汤'
					},{
						'id': 2,
						'name': '草汤'
					},{
						'id': 3,
						'name': '花汤'
					}]
				},{
					id: 3,
					headimg: 'https://img.meituan.net/msmerchant/af6e5f77dca691d39e1583847349f1d0511132.jpg',
					title: '虫草花汤',
					month_sales: '600',
					praise: '33',
					real_price: '2.49',
					past_price: '5',
					goods_type_info: [{
						'id': 1,
						'name': '虫汤'
					},{
						'id': 2,
						'name': '草汤'
					},{
						'id': 3,
						'name': '花汤'
					}]
				},{
					id: 4,
					headimg: 'https://img.meituan.net/msmerchant/af6e5f77dca691d39e1583847349f1d0511132.jpg',
					title: '虫草花汤',
					month_sales: '600',
					praise: '33',
					real_price: '2.49',
					past_price: '5',
					goods_type_info: [{
						'id': 1,
						'name': '虫汤'
					},{
						'id': 2,
						'name': '草汤'
					},{
						'id': 3,
						'name': '花汤'
					}]
				},{
					id: 5,
					headimg: 'https://img.meituan.net/msmerchant/af6e5f77dca691d39e1583847349f1d0511132.jpg',
					title: '虫草花汤',
					month_sales: '600',
					praise: '33',
					real_price: '2.49',
					past_price: '5',
					goods_type_info: [{
						'id': 1,
						'name': '虫汤'
					},{
						'id': 2,
						'name': '草汤'
					},{
						'id': 3,
						'name': '花汤'
					}]
				},{
					id: 6,
					headimg: 'https://img.meituan.net/msmerchant/af6e5f77dca691d39e1583847349f1d0511132.jpg',
					title: '虫草花汤',
					month_sales: '600',
					praise: '33',
					real_price: '2.49',
					past_price: '5',
					goods_type_info: [{
						'id': 1,
						'name': '虫汤'
					},{
						'id': 2,
						'name': '草汤'
					},{
						'id': 3,
						'name': '花汤'
					}],
					label_id: 2
				},{
					id: 7,
					headimg: 'https://img.meituan.net/msmerchant/af6e5f77dca691d39e1583847349f1d0511132.jpg',
					title: '虫草花汤',
					month_sales: '600',
					praise: '33',
					real_price: '2.49',
					past_price: '5',
					goods_type_info: [{
						'id': 1,
						'name': '虫汤'
					},{
						'id': 2,
						'name': '草汤'
					},{
						'id': 3,
						'name': '花汤'
					}],
					label_id: 2
				}]
			}
        }
    },
    created() {
        let that = this
        uni.getSystemInfo({
            success: function (res) {
                that.screenHeight = res.screenHeight
            }
        });
    },
	onReady() {
		this.getLaberInfo()
	},
    computed: {
        goodsHeight: function(){
            return this.screenHeight - 246
        }
    },
	methods: {
		switchLabel: function(label_id){
			this.select_label = label_id
			this.into_view = 'goods'+label_id
			this.leftClick = true
		},
		goodScroll:  function(event){
			if(this.leftClick){
				this.leftClick = false
				return false
			}
			let scrollTop = event.detail.scrollTop
			for(let i = 0; i < this.topList.length ; i++){
				let top1 = this.topList[i];
				let top2 = this.topList[i+1];
				if(scrollTop< this.topList[0]){
					this.select_label = 1
				}else{
					if(scrollTop>=top1&&scrollTop<top2){
						this.select_label = this.label.rows[i+1].id;
					}
				}
			}
			
		},
		getLaberInfo: function(){
			const query =uni.createSelectorQuery().in(this);
			query.selectAll('.goods-list').boundingClientRect().exec(res => {
				let arry = []
				res[0].map(item=>{
					arry.push(item.top)
				});
				this.topList = arry
			})
		},
		goodsTypeInfoModel: function(goods_id) {
			let goods_type = []
			this.list.rows.forEach(v => {
				if(goods_id == v.id){
					goods_type = v.goods_type_info
				}
			})
			
			this.$emit('showModel',{
				show: true,
				goods_type: goods_type,
			})
		}
	},
}
</script>

<style lang="scss">
    .goods-wrap{
        position: relative;
		.goods-left{
		    position: absolute;
		    top: 0;
		    left: 0;
		    bottom: 0;
		    width: 150rpx;
		    background-color: #e1e3ea;
			.goods-left-box{
				padding-bottom: 80rpx;
				&>view{
				    height: 100rpx;
				    line-height: 100rpx;
				    text-align: center;
				    color: #5a6586;
					&.active{
						background-color: #fff;
						color: #333;
						font-weight: bold;
						font-size: 30rpx;
					}
				}
			}
		}
		.goods-right{
			width: 570rpx;
			padding-left: 180rpx;
			background-color: #fff;
			.goods-right-box{
				padding-bottom: 220rpx;
			}
			.goods-list{
				position: relative;
			    padding: 20rpx 20rpx 20rpx 0;
				.goods-info-image{
				    display: inline-block;
				    vertical-align: top;
				    width: 80px;
				    height: 80px;
				    background-size: cover;
				    background-size: center;
				    background-image: url(https://img.meituan.net/msmerchant/af6e5f77dca691d39e1583847349f1d0511132.jpg)
				}
				.goods-info-box{
				    position: relative;
				    width: 330rpx;
				    height: 160rpx;
				    display: inline-block;
				    vertical-align: top;
				    margin-left: 20rpx;
				}
				.goods-info-num{
				    font-size: 24rpx;
				    color: #5a6586;
				}
				.goods-info-price-box{
				    position: absolute;
				    bottom: 0;
				    left: 0;
				    height: 28rpx;
				}
				.goods-info-price{
				    color: #fe587a;
				}
				.goods-info-tip{
				    font-size: 24rpx;
				    color: #5a6586;
				}
				.goods-info-original{
				    font-size: 22rpx;
				    color: #8891ab;
				    text-decoration: line-through;
				    margin-left: 20rpx;
				}
			}
			.select-type{
			    position: absolute;
			    right: 30rpx;
			    bottom: 0;
			    font-size: 24rpx;
			    width: 120rpx;
			    height: 60rpx;
			    line-height: 60rpx;
			    text-align: center;
			    border-radius: 30rpx;
			    background-color: #ffd369;
			}
		}
    }
    
</style>
