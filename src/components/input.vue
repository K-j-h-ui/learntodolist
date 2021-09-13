<template>
	<section class="todo-input">
		<input type="text" placeholder="请输入要添加的事项" v-model="text"  v-on:input="inputText"/><!--1  把text绑定到input里面，更改text值，input中会改变，改变input中的值，text值会也改变-->
		<button v-on:click="addItem">添加</button>
	</section>
</template>

<script>

export default{
	data(){
		return{
			text:''
		}
	},
	methods:{
		inputText(e){//2
		this.text = e.target.value//.e.target.value获取的就是你选择接受事件的元素输入的或者选择的值。
		},
		addItem(){
		this.$emit('addItem',this.text)//this.list.push(this.text)//把text值push到list中
		this.text = ''
		}
	}
}
</script>

<style>
</style>
