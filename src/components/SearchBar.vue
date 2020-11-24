<template lang='pug'>
	form(id='search-form' name='search-form' v-on:submit.prevent='onSubmit')
		input.form-control(v-model='search' type='text' placeholder='검색해보세요' autofocus)
		i.fa.fa-times-circle.bt-reset(v-show='search.length' v-on:click='onReset')
</template>

<script>
export default {
	name: 'search-bar',
	data(){
		return{
			search: '',
		}
	},
	methods :{
		// 부모에게 데이터를 보낼때 이벤트로 보냄, 받을때는 변수로 받음
	
		onSubmit(e) {
			//$emit == dispatch이벤트
			this.$emit('@submit', this.search);
		},
			onReset(e) {
			this.search = '';
		}
	}
}
</script>

<style lang='scss' scoped>
	form {
		margin: 2em 0;
		border: 1px solid #ccc;
		border-radius: 6px;
		padding: 1em;
		position: relative;
		input {
			&:focus {
			box-shadow: none;
			outline:none !important;
		}
		}
		.bt-reset {
			position: absolute; 
			right: 24px;
			top: 50%;
			transform: translateY(-50%);
			cursor: pointer;
		}
	}
</style>