<template>
	<div class="advert">
		<Search></Search>
		<Sort></Sort>
		<List></List>
	</div>
</template>

<script>
	import Search from './components/search.vue'
	import Sort from './components/sort.vue'
	import List from './components/list.vue'
	export default {
		components: {
			Search,
			Sort,
			List
		},
		data() {
			return {
				
			}
		},
		created () {
			
		},
		methods: {
			
		}
	}
</script>

<style lang="scss">
	.advert{
		height: 300rpx;
		background-color: #red;
		.bg{
			width: 100%;
			height: 300rpx;
		}
	}
</style>
 