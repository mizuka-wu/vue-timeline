<template>
  <section class="vue-timeline-container vue-timeline">
    <div class="vue-timeline-block">
      <div class="vue-timeline-img vue-picture">
        <img src="http://7xnlea.com1.z0.glb.clouddn.com/vue-icon-picture.svg" alt="Picture">
      </div>

      <div class="vue-timeline-content">
        <h2>HTML5+CSS3实现的响应式垂直时间轴</h2>
        <p>网页时间轴一般用于展示以时间为主线的事件，如企业网站常见的公司发展历程等。本文将给大家介绍一款基于HTML5和CSS3的漂亮的垂直时间轴，它可以响应页面布局，适用于HTML5开发的PC和移动手机WEB应用。</p>
        <a href="http://www.helloweba.com/view-blog-285.html" class="vue-read-more" target="_blank">阅读全文</a>
        <span class="vue-date">2015-01-06</span>
      </div>
    </div>
    <div class="vue-timeline-block">
      <div class="vue-timeline-img vue-movie">
        <img src="http://7xnlea.com1.z0.glb.clouddn.com/vue-icon-movie.svg" alt="Movie">
      </div>

      <div class="vue-timeline-content">
        <h2>jQuery+PHP动态数字展示效果</h2>
        <p>我们在一些应用中需要动态展示数据，比如当前在线人数，当前交易总额，当前汇率等等，前端页面需要实时刷新获取最新数据。本文将结合实例给大家介绍使用jQuery和PHP来实现动态数字展示效果。</p>
        <a href="http://www.helloweba.com/view-blog-284.html" class="vue-read-more" target="_blank">阅读全文</a>
        <span class="vue-date">2014-12-25</span>
      </div>
    </div>
    <div class="vue-timeline-block">
      <div class="vue-timeline-img vue-picture">
        <img src="http://7xnlea.com1.z0.glb.clouddn.com/vue-icon-picture.svg" alt="Picture">
      </div>

      <div class="vue-timeline-content">
        <h2>PHP操作Session和Cookie</h2>
        <p>我们跟踪用户信息时需要用到Session和Cookie，比如用户登录验证、记录用户浏览历史，存储购物车数据，限制用户会话有效时间等。今天我们来了解下PHP是如何操作Session和Cookie的。</p>
        <a href="http://www.helloweba.com/view-blog-283.html" class="vue-read-more" target="_blank">阅读全文</a>
        <span class="vue-date">2014-12-20</span>
      </div>
    </div>
    <div class="vue-timeline-block">
      <div class="vue-timeline-img vue-movie">
        <img src="http://7xnlea.com1.z0.glb.clouddn.com/vue-icon-movie.svg" alt="Movie">
      </div>

      <div class="vue-timeline-content">
        <h2>jQuery数字加减插件</h2>
        <p>
          我们在网上购物提交订单时，在网页上一般会有一个选择数量的控件，要求买家选择购买商品的件数，开发者会把该控件做成可以通过点击实现加减等微调操作，当然也可以直接输入数字件数。本文将介绍常见的几种使用spinner数字微调器来实现数字加减的功能的方法。</p>
        <a href="http://www.helloweba.com/view-blog-282.html" class="vue-read-more" target="_blank">阅读全文</a>
        <span class="vue-date">2014-12-14</span>
      </div>
    </div>
    <div class="vue-timeline-block">
      <div class="vue-timeline-img vue-movie">
        <img src="http://7xnlea.com1.z0.glb.clouddn.com/vue-icon-location.svg" alt="Location">
      </div>

      <div class="vue-timeline-content">
        <h2>收集整理的非常有用的PHP函数</h2>
        <p>项目中经常会需要一些让人头疼的函数，作为开发者应该整理一个自己的函数库，在需要之时复制过来即可。本文作者收集整理数十个PHP项目中常用的函数，保证能正常运行，你只要复制粘贴到你项目中即可。</p>
        <a href="http://www.helloweba.com/view-blog-281.html" class="vue-read-more" target="_blank">阅读全文</a>
        <span class="vue-date">2014-12-05</span>
      </div>
    </div>
  </section>
</template>
<style scoped>
  .vue-timeline-container {
    /* this class is used to give a max-width to the element it is applied to, and center it horizontally when it reaches that max-width */
    width: 90%;
    max-width: 1170px;
    margin: 0 auto;
  }

  .vue-timeline-container::after {
    /* clearfix */
    content: '';
    display: table;
    clear: both;
  }

  /* --------------------------------

  Main components

  -------------------------------- */

  .vue-timeline {
    position: relative;
    padding: 2em 0;
    margin-top: 2em;
    margin-bottom: 2em;
  }

  .vue-timeline::before {
    /* this is the vertical line */
    content: '';
    position: absolute;
    top: 0;
    left: 18px;
    height: 100%;
    width: 4px;
    background: #d7e4ed;
  }

  @media only screen and (min-width: 1170px) {
    .vue-timeline {
      margin-top: 3em;
      margin-bottom: 3em;
    }

    .vue-timeline::before {
      left: 50%;
      margin-left: -2px;
    }
  }

  .vue-timeline-block {
    position: relative;
    margin: 2em 0;
  }

  .vue-timeline-block:after {
    content: "";
    display: table;
    clear: both;
  }

  .vue-timeline-block:first-child {
    margin-top: 0;
  }

  .vue-timeline-block:last-child {
    margin-bottom: 0;
  }

  @media only screen and (min-width: 1170px) {
    .vue-timeline-block {
      margin: 4em 0;
    }

    .vue-timeline-block:first-child {
      margin-top: 0;
    }

    .vue-timeline-block:last-child {
      margin-bottom: 0;
    }
  }

  .vue-timeline-img {
    position: absolute;
    top: 0;
    left: 0;
    width: 40px;
    height: 40px;
    border-radius: 50%;
    box-shadow: 0 0 0 4px white, inset 0 2px 0 rgba(0, 0, 0, 0.08), 0 3px 0 4px rgba(0, 0, 0, 0.05);
  }

  .vue-timeline-img img {
    display: block;
    width: 24px;
    height: 24px;
    position: relative;
    left: 50%;
    top: 50%;
    margin-left: -12px;
    margin-top: -12px;
  }

  .vue-timeline-img.vue-picture {
    background: #75ce66;
  }

  .vue-timeline-img.vue-movie {
    background: #c03b44;
  }

  .vue-timeline-img.vue-location {
    background: #f0ca45;
  }

  @media only screen and (min-width: 1170px) {
    .vue-timeline-img {
      width: 60px;
      height: 60px;
      left: 50%;
      margin-left: -30px;
      /* Force Hardware Acceleration in WebKit */
      -webkit-transform: translateZ(0);
      -webkit-backface-visibility: hidden;
    }

    .cssanimations .vue-timeline-img.is-hidden {
      visibility: hidden;
    }

    .cssanimations .vue-timeline-img.bounce-in {
      visibility: visible;
      -webkit-animation: vue-bounce-1 0.6s;
      -moz-animation: vue-bounce-1 0.6s;
      animation: vue-bounce-1 0.6s;
    }
  }

  .vue-timeline-content {
    position: relative;
    margin-left: 60px;
    background: white;
    border-radius: 0.25em;
    padding: 1em;
    box-shadow: 0 3px 0 #d7e4ed;
  }

  .vue-timeline-content:after {
    content: "";
    display: table;
    clear: both;
  }

  .vue-timeline-content h2 {
    color: #303e49;
  }

  .vue-timeline-content p, .vue-timeline-content .vue-read-more, .vue-timeline-content .vue-date {
    font-size: 13px;
    font-size: 0.8125rem;
  }

  .vue-timeline-content .vue-read-more, .vue-timeline-content .vue-date {
    display: inline-block;
  }

  .vue-timeline-content p {
    margin: 1em 0;
    line-height: 1.6;
  }

  .vue-timeline-content .vue-read-more {
    float: right;
    padding: .8em 1em;
    background: #acb7c0;
    color: white;
    border-radius: 0.25em;
  }

  .no-touch .vue-timeline-content .vue-read-more:hover {
    background-color: #bac4cb;
  }

  a.vue-read-more:hover {
    text-decoration: none;
    background-color: #424242;
  }

  .vue-timeline-content .vue-date {
    float: left;
    padding: .8em 0;
    opacity: .7;
  }

  .vue-timeline-content::before {
    content: '';
    position: absolute;
    top: 16px;
    right: 100%;
    height: 0;
    width: 0;
    border: 7px solid transparent;
    border-right: 7px solid white;
  }

  @media only screen and (min-width: 768px) {
    .vue-timeline-content h2 {
      font-size: 20px;
      font-size: 1.25rem;
    }

    .vue-timeline-content p {
      font-size: 16px;
      font-size: 1rem;
    }

    .vue-timeline-content .vue-read-more, .vue-timeline-content .vue-date {
      font-size: 14px;
      font-size: 0.875rem;
    }
  }

  @media only screen and (min-width: 1170px) {
    .vue-timeline-content {
      margin-left: 0;
      padding: 1.6em;
      width: 45%;
    }

    .vue-timeline-content::before {
      top: 24px;
      left: 100%;
      border-color: transparent;
      border-left-color: white;
    }

    .vue-timeline-content .vue-read-more {
      float: left;
    }

    .vue-timeline-content .vue-date {
      position: absolute;
      width: 100%;
      left: 122%;
      top: 6px;
      font-size: 16px;
      font-size: 1rem;
    }

    .vue-timeline-block:nth-child(even) .vue-timeline-content {
      float: right;
    }

    .vue-timeline-block:nth-child(even) .vue-timeline-content::before {
      top: 24px;
      left: auto;
      right: 100%;
      border-color: transparent;
      border-right-color: white;
    }

    .vue-timeline-block:nth-child(even) .vue-timeline-content .vue-read-more {
      float: right;
    }

    .vue-timeline-block:nth-child(even) .vue-timeline-content .vue-date {
      left: auto;
      right: 122%;
      text-align: right;
    }

    .cssanimations .vue-timeline-content.is-hidden {
      visibility: hidden;
    }

    .cssanimations .vue-timeline-content.bounce-in {
      visibility: visible;
      -webkit-animation: vue-bounce-2 0.6s;
      -moz-animation: vue-bounce-2 0.6s;
      animation: vue-bounce-2 0.6s;
    }
  }

  @media only screen and (min-width: 1170px) {
    /* inverse bounce effect on even content blocks */
    .cssanimations .vue-timeline-block:nth-child(even) .vue-timeline-content.bounce-in {
      -webkit-animation: vue-bounce-2-inverse 0.6s;
      -moz-animation: vue-bounce-2-inverse 0.6s;
      animation: vue-bounce-2-inverse 0.6s;
    }
  }

</style>
<script>
  export default{
    data () {
      return {}
    },
    components: {}
  }
</script>
