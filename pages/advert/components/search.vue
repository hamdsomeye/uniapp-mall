<template>
	<div class="serach-box">
		<u-search placeholder="搜索商品"></u-search>
		<u-swiper class="swiper-banner" :effect3d="true" :list="list" mode="rect"></u-swiper>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				list: [{
					image: 'http://img13.360buyimg.com/pop/s590x470_jfs/t1/135367/9/7234/100878/5f3ba809E1b202a8b/81b0be8389b4089a.jpg.webp',
				},{
					image: 'https://cdn.uviewui.com/uview/swiper/2.jpg'
				},{
					image: 'https://cdn.uviewui.com/uview/swiper/3.jpg'
				}]
			}
		}
	}
</script>

<style lang="scss">
	.serach-box{
		padding: 18rpx 30rpx;
		background-color: #ffffff;
	}
	.swiper-banner{
		display: block;
		margin-top: 18rpx;
	}
</style>
