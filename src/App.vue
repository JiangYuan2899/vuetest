<template>
    <div id="app">
        {{msg}}

        <v-home></v-home>
    </div>
</template>
<script>
/**
 * 1.引入组件
 * 2.挂载组件
 * 3.在模版中使用
 */
import Home from './components/Home.vue';
export default{
    data(){
        return{
            msg:'你好vue'
        }
    },
    methods:{
    
    },
    components:{
        'v-home':Home
    }


}
</script>