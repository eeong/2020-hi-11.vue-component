<template lang='pug'>
	.prd-wrapper
		product

</template>

<script>
import Product from './Product.vue'

export default {
	name: 'product-wrapper',
	components: {
		'product' : Product,
	},
	data (){
		return {

		}
	},

}
</script>

<style>

</style>