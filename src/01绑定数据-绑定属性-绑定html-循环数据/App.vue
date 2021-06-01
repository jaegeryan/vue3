<template>
  <div>
    <h1>{{ msg }}</h1>
    <h3>绑定数据</h3>
    <p>绑定对象：{{ userInfo.username }}</p>
    <p>
      {{ h2 }}
    </p>
    <p>绑定html标签：
      <sapn v-html="h2"></sapn>
    </p>
    <br>
    <!--- 绑定图片数据---><img alt="思密达" v-bind:src="logoSrc">
    <br>
    <img :src="logoSrc" alt="GG思密达">
    <br>
    <div title="bihaofdsagdsgfdbshjbgjfdsbkgbfjdds">点我试试看</div>
    <br>
    <div :title="title">再点我试试看？</div>

    <h3>绑定属性</h3>
    <a v-bind:[myHref]="'https://www.baidu.com'">跳转百度</a>
    <br>
    <br>
    <a :[myHref]="myLink">跳转到谷歌</a>
    <H3>循环遍历组</H3>
    <ul>
      <!--循环遍历例1-->
      <li v-for="(item,index) in list1" :key="index"> <!--//key也是动态的，所以要写成v-bind:key或者 :key-->
        {{ item }}--{{ index }}
      </li>

      <br>
      <!--循环遍历例2 list 单循环-->
      <li v-for="(item,index) in list2" :key="index">
        {{ item.title }}
      </li>
      <br>
      <!--循环遍历例3  list in list 嵌套循环-->
      <li v-for="(item,index) in list3" :key="index">
        {{ item.cate }}
        <ol>
          <li v-for="(i,k) in item.list" :key="k">
            {{ i.title }}
          </li>
        </ol>
      </li>
      <li v-for="(value,key,index) in myObject" :key="index">
        {{ key }}: {{ value }}---{{ index }}
      </li>
    </ul>


  </div>
</template>
<script>
export default {
  data: function () {
    return {
      msg: '你好',
      userInfo: { //对象 object
        username: '张三',
        age: 20
      },
      h2: '<h2>nihao</h2>',
      logoSrc: "http://1812.img.pp.sohu.com.cn/images/blog/2009/11/18/18/8/125b6560a6ag214.jpg",
      title: "自定义属性值",
      myHref: "href",
      myLink: 'HTTPS://WWW.GOOGLE.COM',
      list1: ['G', 'V', 'AD', 'B', 'G', 'A', 'D', 'FDSA', 'F'],
      list2: [{
        title: "新闻1+1"
      }, {
        title: "新闻30分"
      }, {
        title: "午间新闻"
      }],
      list3: [{
        "cate": "国内新闻",
        "list": [{
          'title': '上海新闻'
        }, {
          'title': '北京快讯'
        }]
      }, {
        "cate": '国际新闻',
        "list": [{
          'title': '叙利亚冲突'
        }, {
          'title': '美国战报'
        }]
      }],
      myObject: {
        title: 'How to do lists in Vue',
        author: 'Jaeger Yan',
        publishedAt: '2020-03-22'

      }
    }
  }
}
</script>

<style>
</style>
