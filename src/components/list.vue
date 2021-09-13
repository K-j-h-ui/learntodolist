<template>
	<section>
		<ul class="todo-list" v-show="childrenList.length" >
			<li class="todo-item" v-for="( item,index ) in childrenList" v-bind:key="index+item"><!--列表渲染-->
				<span>{{index+1}}.</span><p>{{item}}</p><button @click="removeItem(index)">完成</button>
			</li>
		
		</ul>
		<div class="todo-nodata" v-show="!childrenList.length"><!--v-if和v-else在元素切换不频繁的场景中使用 -->
			还没有数据，请及时添加！
		</div>
	</section>
</template>

<script>

export default{
	props:{
		childrenList:{type:Array}
	},

	methods:{
		removeItem(index){
		this.$emit('removeItem',index)
		
		}
	}

}
</script>

<style>
</style>
