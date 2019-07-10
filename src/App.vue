<template>
   <div id="app" class="hello">
   <h5>第五讲</h5> 
      <h3>这是一个根组件---------  {{msg}}</h3>
        <br>
          <hr>
          </hr>
        </br>
      <h4>{{obj.name}}</h4>
        <br>
          <hr>
          </hr>
        </br>
      <ul>
        <li v-for="item in list">
          {{item}}
        </li>
      </ul>
        <br>
          <hr>
          </hr>
        </br>
      <ul>
        <li v-for="item in list1">
          {{item.message}}
      </li>
      </ul>  
        <br>
          <hr>
          </hr>
        </br>
      <ul>
        <li v-for="item in list2">
          {{item.cate}}
          <ol>
            <li v-for="news in item.list">
            {{news.title}}
            </li>
          </ol>
        </li>
      </ul>
       <br>
          <hr>
          <h5>第六讲</h5> 
          </hr>
        </br> 
      <div :title="parentMessage">鼠标瞄上去</div>
     <img :src="url" >
     <!--绑定HTML-->
      <div v-html="h"> </div>
      <!--绑定数据另一种方式-->
      <div v-text='msg'></div>
      <!--v-bind:class :class的使用-->
       <div v-bind:class="{'red':flag}">I'm  a div </div> 
      <div :class="{'red':flag,'blue':!flag}">I'm an another div </div> 
      <!-- 循环数据 并显示出索引值-->
      <ul>
        <li v-for="(item,key) in list">
          {{key}}-----{{item}}
        </li>
      </ul>
      <!-- 循环数据 第一个数据高亮索引值是从0开始的 red和bule不用加引号-->
      <ul>
        <li v-for="(item,key) in list" :class="{red:key==0,blue:key==1}">{{item}}</li>
      </ul>
      <!--绑定样式v-bind:style :style的使用 单引号和双引号效果是一样的？？？-->
      <div class="box" v-bind:style="{'width':boxWidth+'PX'}">
      我是一个box  
      </div>
      </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data  () {
    return {
      msg: '这是一个msg',
      obj:{
        name:"这是一个obj的名字"
      },
      parentMessage: '么么哒',
      url:'',
      h:'<h2>我是h2</h2>',
      flag:false,
      boxWidth:500,
      list:["A",'B','C'],
      list1:[
          {message:'A'},
          {message:'B'},
          {message:'C'},
      ],
      list2:[
        {
          "cate":"国内新闻",
          "list":[
              
                {'title':'国内新闻1'},
                {'title':'国内新闻2'}
          ],
        },
        {
          "cate":"国际新闻",
          "list":[
              {'title':'国际新闻1'},
              {'title':'国际新闻2'}
              
          ]
        }
      ]
    }
  }
}
</script>

<style>
  .red{
    color: red
  }
  .blue{
    color: blue
  }
  .box{
    height: 100px;
    width: 100px;
    background: red; 
  }
</style>
