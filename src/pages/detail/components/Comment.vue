<template>
  <div>
    <div class="space"></div>
    <div class="comment-title border-bottom">
      <p><span class="iconfont icon-praise">&#xe715;</span> 用户评论</p>
    </div>
    <div class="comment-item border-bottom">
      <div class="comment-item-title">
        <div class="star"><span class="iconfont">&#xe670;</span><span class="iconfont">&#xe670;</span><span class="iconfont">&#xe670;</span><span class="iconfont">&#xe670;</span><span class="iconfont">&#xe670;</span></div>
        <div class="name">随*啊  2017-12-30</div>
        <p>参观故宫是来京必须要安排的行程，紫禁城的宏伟和惊艳超乎你想象，假装自己穿越时空，你走在乾隆皇帝走过的石板砖上，体验当年盛世的文化底蕴和奢华的生活～ 攻略1 提前网上购买门票，凭身份证直接进 攻略2 租讲解器，每个讲解器都是感应的，每个只讲解一遍，只有一个耳机，别想着两人共用的好事儿，哈哈哈 攻略3 周一闭馆，周末人居多，尽量安排工作日，若所有宫殿都想参观，就提早进去，不过我个人觉得没必要，参观代表性的中轴和个别妃子和慈禧的宫殿即可，建议预留至少大半天时间在里头 再来北京，还愿意去故宫~~</p>
      </div>
    </div>
    <div class="comment-item border-bottom">
      <div class="comment-item-title">
        <div class="star"><span class="iconfont">&#xe670;</span><span class="iconfont">&#xe670;</span><span class="iconfont">&#xe670;</span><span class="iconfont">&#xe670;</span><span class="iconfont">&#xe670;</span></div>
        <div class="name">g*8  2018-03-24</div>
        <p>不错，很方便，集合时需要打出1个小时的富裕时间，因为从天安门地铁出来安检的太严了，赶上人多的话可能需要1个小时，今天是淡季也排了40分钟才进入天安门区域，张敏导游很专业讲解的也很认真，很愉快的一次故宫之旅。</p>
        <div class="gallary" @click="handleBannerClick">
          <div class="gallary-img" v-for="(item,index) in imgList" :key="index">
            <img :src="item" alt="" />
          </div>
        </div>
      </div>
    </div>
    <div class="more">查看更多评论 <span class="iconfont icon-right">&#xe6e0;</span></div>
    <div class="space"></div>
    <comment-gallary :imgs="imgGallary" v-show="showGallary" @close="handleGallaryClose"></comment-gallary>
  </div>
</template>

<script>
  import CommentGallary from 'common/gallary/CommentGallary'
  export default {
    name: 'DetailComment',
    data () {
      return {
        showGallary: false,
        imgList: ['https://imgs.qunarzz.com/piao/fusion/1803/eb/3cecdcc35430f602.jpg_228x168_0dfeb38e.jpg','https://imgs.qunarzz.com/piao/fusion/1803/93/e260dd039cb04c02.jpg_228x168_a5195ec3.jpg','https://imgs.qunarzz.com/piao/fusion/1803/79/eaa288e638c8ff02.jpg_228x168_ee6d3117.jpg','https://imgs.qunarzz.com/piao/fusion/1803/3d/15cd669297228402.jpg_228x168_fadb7e6e.jpg'],
        imgGallary: ['https://imgs.qunarzz.com/piao/fusion/1803/eb/3cecdcc35430f602.jpg','https://imgs.qunarzz.com/piao/fusion/1803/93/e260dd039cb04c02.jpg','https://imgs.qunarzz.com/piao/fusion/1803/79/eaa288e638c8ff02.jpg','https://imgs.qunarzz.com/piao/fusion/1803/3d/15cd669297228402.jpg']
      }
    },
    methods: {
      handleBannerClick () {
        this.showGallary = true
      },
      handleGallaryClose () {
        this.showGallary = false
      }
    },
    components: {
      CommentGallary
    }
  }
</script>

<style lang="stylus" scoped>
  .space
    width: 100%;
    height: 0.3rem;
    background: #eee;
  .comment-title
      p
        height:1rem
        line-height: 1rem;
        color: #444;
        text-indent: .3rem;
        font-size: 0.35rem;
      .icon-praise
        font-size: 0.4rem;
        color: #00bcd4;
  .comment-item
    padding: 0.3rem 0.2rem 0.1rem
    overflow: hidden;
    .star
      float: left;
      color: #ffb436;
    .name
      float: right;
    p
      width: 100%;
      float: left;
      line-height: .4rem;
      font-size: 0.26rem;
      color: #666;
      padding: 0.15rem 0;
    .gallary
      float: left;
      .gallary-img
        display: inline-block;
        width: 50%
        padding:.1rem
        box-sizing:border-box
        img
          width: 100%;
  .more
    text-align: center
    line-height: 0.8rem;
    border-top: 1px dashed #ccc;
</style>