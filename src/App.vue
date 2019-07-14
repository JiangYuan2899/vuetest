<template>

	<div id='app'>
	<br>
	第七讲数组增加和删除
	<hr>
	</hr>
	</br>
			<input type="text" v-model='todo' @keydown ='doAdd($event)'>
			<button @click='doAdd()'>增加</button>

			<br>
			<hr>
			</hr>
			</br>
			<h2>进行中</h2>
				<ul>
					<li v-for='(item,key) in list' v-if='!item.checked'>
					<input type="checkbox" v-model='item.checked'>	{{item.title}} -----<button @click='doDele(key)'>删除
					</button>
					</li>
				</ul>
				<h2>已完成</h2>
				<ul>
					<li v-for='(item,key) in list' v-if='item.checked'>
					<input type="checkbox" v-model='item.checked'>	{{item.title}} -----<button @click='doDele(key)'>删除
					</button>
					</li>
				</ul>
				<!-- <h2 v-if='ok'>这是一个yes</h2>
				<h2 v-if='!ok'>这是一个no</h2> -->
				<button @click='getlist()'>获取list </button>
	</div> 
</template>
<script>


	export default{
		data(){
			return {
			ok:false,
			todo:'',
			list:[
				{
					title:'录制node.js',
					checked:false,

				},
				{
					title:'录制react.js',
					checked:true,
				},
			]
			}
		},
	methods:{
		doAdd(e){
			console.log(e.keyCode )
			if(e.keyCode==13){
			// alert('增加');
			//1、获取文本框输入的值 2、把文本框的值push到list里面
			this.list.push(
				{
					title:this.todo,
					checked:false,
				});
			this.todo='';
			}
		},
		doDele(key){
			//js里面 操作数组的方法
			this.list.splice(key,1);
		},
		getlist(){
			console.log(this.list)	
		} 
	}
}

</script>
<style>

</style>