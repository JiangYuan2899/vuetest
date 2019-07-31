<template>
<!--所有内容要被根节点包含起来  -->
    <div>
    <h2>这是一个首页组件{{msg}}</h2>
    <button @click="run()">执行run方法  </button>
    </div>
</template>
<script>
export default {
    data(){
        return{
            msg:'我这是一个首页'
        }
    },
    methods:{
        run(){
            alert(this.msg)
        }
    }
}
</script>
