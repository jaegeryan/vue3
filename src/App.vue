<template>
  <div>
    <h1>{{msg}}</h1>
    <button @click="setMsg()">触发方法设置msg的值</button>
    <br>
    <br>
    <button @click="getMsg()">获取方法msg的值</button>
    <br>
    <br>
    <button @click = "changeClass()">点我换色</button>
    <div :class = "myClass">
    </div>
    <br>
    <h2>绑定多个class</h2>

  </div>
</template>
<script>
  export default {
    data() {
      return {
        msg: '你好',
        myClass: "red"
      };
    },
    methods:{
      setMsg(){
        this.msg = '我是改变后的值'
      },
      getMsg(){
        alert(this.msg)
      },
      changeClass(){
        this.myClass = "blue"
      }
    }
  }
</script>

<style>
.red{
  background: #42b983;
  width: 100px;
  height: 133px;
}
.blue{
  background: #21bdc6;
  width: 100px;
  height: 133px;
}
</style>
