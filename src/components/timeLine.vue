<template>
  <section class="timeline-container timeline">
    <div @click="changeCurrentTimePoint(point)" v-for="point in points" class="timeline-block">
      <div class="timeline-img" :class="['timeline-img',point.pointColor===undefined?'red':point.pointColor]">
        <img v-if="point.img" :src="getImg(point.img)" alt="">
      </div>

      <div class="timeline-content">
        <h2 v-text="point.title"></h2>
        <p v-text="point.text"></p>
        <a :href="point.linkUrl"
           class="read-more"
           target="_blank"
           v-if="point.linkUrl"
           v-html="point.linkText!=undefined?point.linkText:'Read more'"
        ></a>
        <span v-if="point.date" class="date" v-text="point.date"></span>
      </div>
    </div>
  </section>
</template>
<style scoped>
  .timeline-container {
    /* this class is used to give a max-width to the element it is applied to, and center it horizontally when it reaches that max-width */
    width: 90%;
    max-width: 1170px;
    margin: 0 auto;
  }

  .timeline-container::after {
    /* clearfix */
    content: '';
    display: table;
    clear: both;
  }

  /* --------------------------------

  Main components

  -------------------------------- */

  .timeline {
    position: relative;
    padding: 2em 0;
    margin-top: 2em;
    margin-bottom: 2em;
  }

  .timeline::before {
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
    .timeline {
      margin-top: 3em;
      margin-bottom: 3em;
    }

    .timeline::before {
      left: 50%;
      margin-left: -2px;
    }
  }

  .timeline-block {
    position: relative;
    margin: 2em 0;
  }

  .timeline-block:after {
    content: "";
    display: table;
    clear: both;
  }

  .timeline-block:first-child {
    margin-top: 0;
  }

  .timeline-block:last-child {
    margin-bottom: 0;
  }

  @media only screen and (min-width: 1170px) {
    .timeline-block {
      margin: 4em 0;
    }

    .timeline-block:first-child {
      margin-top: 0;
    }

    .timeline-block:last-child {
      margin-bottom: 0;
    }
  }

  .timeline-img {
    position: absolute;
    top: 0;
    left: 0;
    width: 40px;
    height: 40px;
    border-radius: 50%;
    box-shadow: 0 0 0 4px white, inset 0 2px 0 rgba(0, 0, 0, 0.08), 0 3px 0 4px rgba(0, 0, 0, 0.05);
  }

  .timeline-img img {
    display: block;
    width: 24px;
    height: 24px;
    position: relative;
    left: 50%;
    top: 50%;
    margin-left: -12px;
    margin-top: -12px;
  }

  .timeline-img.green {
    background: #75ce66;
  }

  .timeline-img.red {
    background: #c03b44;
  }

  .timeline-img.yellow {
    background: #f0ca45;
  }

  @media only screen and (min-width: 1170px) {
    .timeline-img {
      width: 60px;
      height: 60px;
      left: 50%;
      margin-left: -30px;
      /* Force Hardware Acceleration in WebKit */
      -webkit-transform: translateZ(0);
      -webkit-backface-visibility: hidden;
    }

    .cssanimations .timeline-img.is-hidden {
      visibility: hidden;
    }

    .cssanimations .timeline-img.bounce-in {
      visibility: visible;
      -webkit-animation: bounce-1 0.6s;
      -moz-animation: bounce-1 0.6s;
      animation: bounce-1 0.6s;
    }
  }

  .timeline-content {
    position: relative;
    margin-left: 60px;
    background: white;
    border-radius: 0.25em;
    padding: 1em;
    box-shadow: 0 3px 0 #d7e4ed;
  }

  .timeline-content:after {
    content: "";
    display: table;
    clear: both;
  }

  .timeline-content h2 {
    color: #303e49;
  }

  .timeline-content p, .timeline-content .read-more, .timeline-content .date {
    font-size: 13px;
    font-size: 0.8125rem;
  }

  .timeline-content .read-more, .timeline-content .date {
    display: inline-block;
  }

  .timeline-content p {
    margin: 1em 0;
    line-height: 1.6;
  }

  .timeline-content .read-more {
    float: right;
    padding: .8em 1em;
    background: #acb7c0;
    color: white;
    border-radius: 0.25em;
  }

  .no-touch .timeline-content .read-more:hover {
    background-color: #bac4cb;
  }

  a.read-more:hover {
    text-decoration: none;
    background-color: #424242;
  }

  .timeline-content .date {
    float: left;
    padding: .8em 0;
    opacity: .7;
  }

  .timeline-content::before {
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
    .timeline-content h2 {
      font-size: 20px;
      font-size: 1.25rem;
    }

    .timeline-content p {
      font-size: 16px;
      font-size: 1rem;
    }

    .timeline-content .read-more, .timeline-content .date {
      font-size: 14px;
      font-size: 0.875rem;
    }
  }

  @media only screen and (min-width: 1170px) {
    .timeline-content {
      margin-left: 0;
      padding: 1.6em;
      width: 45%;
    }

    .timeline-content::before {
      top: 24px;
      left: 100%;
      border-color: transparent;
      border-left-color: white;
    }

    .timeline-content .read-more {
      float: left;
    }

    .timeline-content .date {
      position: absolute;
      width: 100%;
      left: 122%;
      top: 6px;
      font-size: 16px;
      font-size: 1rem;
    }

    .timeline-block:nth-child(even) .timeline-content {
      float: right;
    }

    .timeline-block:nth-child(even) .timeline-content::before {
      top: 24px;
      left: auto;
      right: 100%;
      border-color: transparent;
      border-right-color: white;
    }

    .timeline-block:nth-child(even) .timeline-content .read-more {
      float: right;
    }

    .timeline-block:nth-child(even) .timeline-content .date {
      left: auto;
      right: 122%;
      text-align: right;
    }

    .cssanimations .timeline-content.is-hidden {
      visibility: hidden;
    }

    .cssanimations .timeline-content.bounce-in {
      visibility: visible;
      -webkit-animation: bounce-2 0.6s;
      -moz-animation: bounce-2 0.6s;
      animation: bounce-2 0.6s;
    }
  }

  @media only screen and (min-width: 1170px) {
    /* inverse bounce effect on even content blocks */
    .cssanimations .timeline-block:nth-child(even) .timeline-content.bounce-in {
      -webkit-animation: bounce-2-inverse 0.6s;
      -moz-animation: bounce-2-inverse 0.6s;
      animation: bounce-2-inverse 0.6s;
    }
  }

</style>
<script>
  export default{
    props: {
      points: {
        required: true
      }
    },
    data () {
      return {
        defaultImg: 'data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBzdGFuZGFsb25lPSJubyI/PjwhRE9DVFlQRSBzdmcgUFVCTElDICItLy9XM0MvL0RURCBTVkcgMS4xLy9FTiIgImh0dHA6Ly93d3cudzMub3JnL0dyYXBoaWNzL1NWRy8xLjEvRFREL3N2ZzExLmR0ZCI+PHN2ZyB0PSIxNDg2OTExMDgyNTYzIiBjbGFzcz0iaWNvbiIgc3R5bGU9IiIgdmlld0JveD0iMCAwIDEwMjQgMTAyNCIgdmVyc2lvbj0iMS4xIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHAtaWQ9IjIxNDYiIHhtbG5zOnhsaW5rPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hsaW5rIiB3aWR0aD0iMjAwIiBoZWlnaHQ9IjIwMCI+PGRlZnM+PHN0eWxlIHR5cGU9InRleHQvY3NzIj48L3N0eWxlPjwvZGVmcz48cGF0aCBkPSJNMzYxLjU2NTEwNSAwbDI5Ni44NzcxNjkgMCAwIDk3LjYwNzMxMy0yOTYuODc3MTY5IDAgMC05Ny42MDczMTNaIiBwLWlkPSIyMTQ3Ij48L3BhdGg+PHBhdGggZD0iTTQ2MS4xOTIyMDQgMzQzLjYyOTcyNWw5Ny42MDczMTMgMCAwIDI0NC4wMDI2MjYtOTcuNjA3MzEzIDAgMC0yNDQuMDAyNjI2WiIgcC1pZD0iMjE0OCI+PC9wYXRoPjxwYXRoIGQ9Ik05NTMuMjA1NzEzIDE2Mi42MDA1NjlsLTY5LjAwMTUxMy02OS4wMDE1MTMtMTI3LjcwMDU1MyAxMjcuNzAwNTUzYy03MC4yODU0MDctNDcuNzU0NjIxLTE1NS4xMTY0MDMtNzUuNzAyODE3LTI0Ni40OTIxMjktNzUuNzAyODE3QzI2Ny40MzM3MDEgMTQ1LjU5Njc5MyA3MC43OTQyNjUgMzQyLjIyMDU3MiA3MC43OTQyNjUgNTg0Ljc5ODM4OWMwIDI0Mi41NjIxNTkgMTk2LjYzOTQzNyA0MzkuMjAxNTk2IDQzOS4yMDE1OTYgNDM5LjIwMTU5NiAyNDIuNTc3ODE2IDAgNDM5LjIwMTU5Ni0xOTYuNjM5NDM3IDQzOS4yMDE1OTYtNDM5LjIwMTU5NiAwLTExNS45MjYyOTktNDUuMjQ5NDYtMjIxLjA0OTA5NC0xMTguNjM1MDA0LTI5OS41NTQ1NTlMOTUzLjIwNTcxMyAxNjIuNjAwNTY5ek04NTEuNjA1OCA1ODQuNzk4Mzg5YzAgMTg4LjY1NDIzOC0xNTIuOTQwMDQ0IDM0MS42MDk5NC0zNDEuNjA5OTQgMzQxLjYwOTk0UzE2OC40MDE1NzggNzczLjQ1MjYyNyAxNjguNDAxNTc4IDU4NC43OTgzODljMC0xODguNjY5ODk1IDE1Mi45NDAwNDQtMzQxLjYwOTk0IDM0MS42MDk5NC0zNDEuNjA5OTRTODUxLjYwNTggMzk2LjEyODQ5NCA4NTEuNjA1OCA1ODQuNzk4Mzg5eiIgcC1pZD0iMjE0OSI+PC9wYXRoPjwvc3ZnPg=='
      }
    },
    components: {},
    methods: {
      getImg: function (imgurl) {
        var ImgObj = new Image() // 判断图片是否存在
        ImgObj.src = imgurl
        // 没有图片，则返回-1
        if (ImgObj.fileSize > 0 || (ImgObj.width > 0 && ImgObj.height > 0)) {
          return imgurl
        } else {
          return this.defaultImg
        }
      },
      changeCurrentTimePoint: function (point) {
        this.$on('currentPoint', point)
      }
    }
  }
</script>
