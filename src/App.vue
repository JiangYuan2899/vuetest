<template>
  <!-- <div id="app" :class="[activeClass, errorClass]"> -->
    <!-- <img src="./assets/logo.png"> -->
    <router-view/>

  </div>
</template>

<script>
//在vue里注册组件，定义todo-item的新组件
    Vue.component('todo-item',{
        template:"<li>This is a todo</li>"
    });
    let app=new Vue({
        el:"#app",
    });
    export default {
      name: 'App',
      activeClass:'active',
      errorClass:'text-danger'
    }
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
