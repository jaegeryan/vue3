<template>
  <div>
    {{ msg }}
    <br>
    <br>
    <button @click="getMsg">获取MSG的值</button>
    <br>
    <br>
    <button v-on:click="setMsg">设置MSG的值</button>
    <br>
    <br>
    <h3>{{ title }}</h3>
    <button v-on:click="setTitle('行吧，这是改变后的标题')">设置Title的值</button>
    <br>
    <br>
    <button v-on:click="setTitle('行吧，这是改变后的另一个标题')">设置Title的值</button>
    <br>
    <br>
    <button v-on:click="run()">执行run方法实现方法调用方法</button>
    <br>
    <br>
    <button data-aid="123" @click="eventFn($event)">事件对象</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      msg: "你好",
      title: "我是标题",
    };
  },
  methods: {
    getMsg() {
      alert(this.msg)
    },
    setMsg() {
      this.msg = "这是设置后的MSG的值";
    },
    setTitle(data) {
      this.title = data;
    },
    run(){
      this.getMsg()
    } ,
    eventFn(e){
      console.log(e);
      e.srcElement.style.background = "red";
      console.log(e.srcElement.dataset.aid);
    }
  }
};
</script>
