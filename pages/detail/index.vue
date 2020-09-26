<template>
	<view class="content">
        <uni-header class="header"></uni-header>
        <uni-switch></uni-switch>
        <uni-goods  @showModel="showModel"></uni-goods>
		<uni-footer></uni-footer>
		<uni-goods-type-model :show="show" :goodsType="goods_type"></uni-goods-type-model>
	</view>
</template>

<script>
    import uniHeader from './components/header'
    import uniSwitch from './components/switch'
    import uniGoods from './components/goods'
    import uniFooter from './components/footer'
    import uniGoodsTypeModel from './components/goodsTypeModel'
	export default {
        components: {
            uniHeader,
            uniSwitch,
            uniGoods,
			uniFooter,
			uniGoodsTypeModel
        },
		data() {
			return {
				show: false,
				goods_type: []
			}
		},
		onLoad() {

		},
		methods: {
			showModel: function(v) {
				this.show = v.show
				this.goods_type = v.goods_type
			}
		}
	}
</script>

<style>
	.header {
		width: 100%;
	}
</style>
