<template lang='pug'>
	.container
		.jumbotron
			h1 {{title}}
			small.text-secondary
				i.fa.fa-shopping-cart.mr-3
				span {{subTitle}}
		search-bar(v-on:@sumbit='onSubmit')
		product-wrapper
	
</template>

<script>
import SearchBar from './components/SearchBar.vue'
import ProductWrapper from './components/Product-wrapper.vue'

export default {
	data() {
		return {
			title:'쇼핑몰',
			subTitle:'검색을 통해 상품을 검색하세요',
			search: '',
		}
	},
	components: {
		'search-bar': SearchBar,
		'product-wrapper': ProductWrapper,
	},
	methods: {
		onSubmit(value) {
			this.search = value;
		}
	}
}
</script>

<style lang='scss' scoped>

</style>