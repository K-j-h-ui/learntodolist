<template>
<div id="app">
  <header>TodoList</header>
  <todo-input @addItem='addChildrenItem'/><!--注册组件第一步-->
  <todo-list :childrenList="list" @removeItem="removeChildrenItem"/>
</div>
</template>

<script>
import TodoInput from './components/input'//注册组件第二步
import TodoList from './components/list'
export default {
  name: 'App',
  components:{//注册组件第三步
	TodoInput,
	TodoList
  },
  data(){
	return{
      list:['学习','吃饭','睡觉']
	
	}
  },
  methods:{
	addChildrenItem(val){
		this.list.push(val)
	},

	removeChildrenItem(index){//貌似在方法里的才需要用 @ 符号
	this.list.splice(index)
	}
  }
}
</script>

<style>
ul{
	margin: 0;
	padding: 0;
	list-style: none;
}

#app{
	width: 400px;
	height: 500px;
	margin: 80px auto;
	padding-top:20px ;
}
p{
	margin:0;
}

header{
	font-family: " helvetica, sans-serif";
	font-size: 28px;
	line-height: 40px;
	text-align: center;
}
.todo-input{
	display: flex;
	margin-bottom: 10px;
}
.todo-input input{
	flex: 1;
	height: 34px;
	margin-right: 20px;
	padding-left: 10px;
	border-radius: 6px;
	border: 1px solid #adadad;
	
}
.todo-input button{
	border: none;
	border-radius: 6px;
	width: 70px;
	heigt:36px;
	color: white;
	background-color: blue;
}
.todo-item{
	display: flex;
	height: 40px;
	padding: 0 10px;
	
}
.todo-item span{
	
	padding-right:10px;
	
}
.todo-item p{
	flex: 1;
}
.todo-item button{
	width: 50px;
	height: 32px;
	border: none;
	border-radius: 6px;
	background-color: red;
	color: white;	
}
.todo-nodata{
	font-size: 25px;
	line-height: 80px;
	text-align: center;
	color: #0000FF;
}
</style>
