<template>
  <div id="app">
    <timeLine :points="points"></timeLine>
  </div>
</template>

<script>
  import timeLine from './components/timeLine.vue'

  export default {
    name: 'app',
    data () {
      return {
        points: [{
          pointColor: 'red', // *关键点颜色 可选red yellow green
          img: '1', // 图片地址 可留空
          title: 'hello world', // *时间点标题
          text: 'first post', // *时间点内容
          linkUrl: 'www.baidu.com', // *链接url 留空则不显示按钮
          linkText: 'Read detail', // 按钮显示内容 默认为Read more
          date: '2017-1-1' // 时间点
        }]
      }
    },
    components: {
      timeLine
    }
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
  html body {
    background-color: beige;
  }
</style>
