<template>
  <div>
    <h1>{{ msg }}</h1>
    <button @click="setMsg()">触发方法设置msg的值</button>
    <br>
    <br>
    <button @click="getMsg()">获取方法msg的值</button> <!-- 1.1、v- bind: class 绑定字符串 -->
    <br>
    <div class="red"></div>
    <br>
    <button @click="changeClass()">点我换色</button>
    <div :class="myClass"> <!-- v-bind:class --> 可更换值</div> <!-- 1.2、v- bind: class绑定对象  -->
    <br>
    <h2>class绑定多个属性</h2>
    <div :class="{'active': isActive,'red': isRed }" class="blue"> <!-- 1.3 v-bind: class结合class的使用 -->
      div
    </div>
    <br>
    <div :class="[errorClass, baseClass]">  <!-- 1.4、数组语法 -->
      div
    </div>
    <br>
    <div :class="[flag ? baseClass : errorClass]">  <!-- 1.5、数组语法结合三目运算 -->
      数组语法 结合三目运算绑定
    </div>
    <br>
    <h2>绑定多个Class</h2>
    <div :style="'color:'+color">绑定style</div> <!--绑定单个style-->
    <br>
    <div :style="{'color': activeColor, 'fontSize': fontSize}">
      绑定多个style
    </div> <!--绑定多个style-->
    <br>
    <div :style="styleObject">
      绑定多个style第二种写法
    </div>
    <br>
    <div :style="[baseStyle, orangeStyle]">
      绑定多个style第三种写法 数组的写法
    </div>
    <br>
    <ul>
      <li v-for="(item,index) in list" :key="index" :class="{'red':index===0,'blue':index===1}">
        {{ item }}
      </li>
    </ul>
    <br>
    <ul>
      <li v-for="(item,index) in list" :key="index" :style="[index===0?styleRed:null, index===1?styleBlue:null]"> <!-- 建议使用class -->
        {{ item }}
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  data() {
    return {
      msg: '你好',
      myClass: "red",
      isActive: true,       //这个不写就不显示, 或者写false就不显示
      isRed: false,         // 同上
      errorClass: "error",
      baseClass: "base",
      flag: false,            //在结合三目运算中如果isActive是false，那么就会选用errorClass
      color: "red",
      activeColor: 'blue',
      fontSize: "20px",
      styleObject: {
        color: 'red',
        fontSize: '40px'
      },
      baseStyle: {
        width: "200px",
        height: "200px",
        fontSize: "20px"
      },
      orangeStyle: {
        background: "orange"
      },
      list: ['马化腾', '刘强东', '联想', '马化腾0', '刘强东0', '联想0'],
      styleRed: {
        color: 'red',
      },
      styleBlue: {
        color: 'blue',
      },

    };
  },
  methods: {
    setMsg() {
      this.msg = '我是改变后的值' // 用this.msg修改msg的值
    },
    getMsg() {
      alert(this.msg)
    },
    changeClass() {
      this.myClass = "blue"
    }
  }
}
</script>

<style>
.active {
  display: block;
  font-size: 30px;
  color: burlywood;

}

.error {
  background: mediumspringgreen;
  font-size: 30px;
  color: #825ad0;
}

.base {
  width: 300px;
  height: 333px;
}

.red { /* 第11行中 myClass 的样式修改 */
  background: #ff0000;
  width: 100px;
  height: 133px;
}

.blue {
  background: #21bdc6;
  width: 100px;
  height: 133px;
}
</style>
