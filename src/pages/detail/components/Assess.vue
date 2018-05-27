<template>
  <div class="warp">
    <div class="assess-top border-bottom">
      <div class="assess-top-score border-right">
        <p><span>5.0</span> 分 超赞</p>
        <p>223410条评论  86攻略</p>
      </div>
      <div class="assess-top-intro">
            <p>景点简介</p>
            <p>开放时间、贴士</p>
      </div>
    </div>
    <div class="assess-bottom">
      <span class="iconfont">&#xe611;</span> 北京市东城区景山前街4号 <span class="iconfont icon-right">&#xe6e0;</span>
    </div>
    <div class="notice">
      <p><span class="iconfont">&#xe62a;</span> 除法定节假日，故宫博物院实行周一闭馆。</p>
    </div>
    <div class="ticket">
      <p><span class="iconfont icon-praise">&#xe656;</span> 门票推荐</p>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'DetailAssess'
  }
</script>

<style lang="stylus" scoped>
  .warp
    width: 100%;
    .assess-top
      height: 1.5rem
      .assess-top-score
        box-sizing: border-box
        padding: .2rem .3rem
        width: 50%;
        float: left;
        p
          color: #444;
          font-size: 0.2rem;
          &:first-child
            color: #ff8300;
            font-size: 0.3rem;
            span
              font-size: 0.5rem;
          &:last-child
            color: #777;
            line-height: .5rem;
      .assess-top-intro
        box-sizing: border-box
        padding: .35rem .3rem
        width: 50%;
        float: right;
        p
          color: #444;
          font-size: 0.2rem;
          &:first-child
            color: #444;
            font-weight: bold;
            font-size: 0.3rem;
          &:last-child
            color: #777;
            line-height: .5rem;
    .assess-bottom
      line-height: 1rem;
      text-indent: 0.3rem;
      .icon-right
        float: right;
        font-size: .4rem;
        margin-right: 0.3rem;
    .notice
      height: 1.2rem
      padding-top: .2rem
      background: #eee;
      p
        height:1rem
        line-height: 1rem;
        color: #ff8300;
        background: #fff5e5;
        text-indent: .3rem;
    .ticket
      border-bottom: 1px solid #ccc
      margin-bottom: 0.2rem;
      p
        height:1rem
        line-height: 1rem;
        color: #444;
        text-indent: .3rem;
        font-size: 0.35rem;
      .icon-praise
        font-size: 0.4rem;
        color: red;
</style>