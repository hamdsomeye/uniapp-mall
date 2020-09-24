<template>
	<div class="tabBar" :style="{'margin-top': barHeight.statusBarHeight+'px',height: barHeight.titleVarHeight+'px'}">
		<p class="tabBar-title">{{title}}</p>
	</div>
</template>

<script>
	import { mapState } from 'vuex'
	export default {
		props: {
			title: {
				type: String , default: 'xxx'
			},
		},
		computed: {
			...mapState(['barHeight'])
		},
		created() {
			if(uni.getStorageSync('barHeight').statusBarHeight) {
				this.$store.state.barHeight = uni.getStorageSync('barHeight')
			}else{
				this.isBarHeight().then((isTemp) => {
					this.$store.state.barHeight = isTemp
					uni.setStorageSync('barHeight',isTemp)
				})
			}
			console.log(this)
		},
	}
</script>

<style lang="scss">
	.tabBar{
		position: relative;
		p{
			position: absolute;
			top: 50%;
			transform: translateY(-50%);
			width: 100%;
			font-size: 32rpx;
			font-weight: bold;
			line-height: 32rpx;
			text-align: center;
		}
	}
</style>
