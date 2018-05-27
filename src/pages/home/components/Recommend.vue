<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <router-link tag='li' class="item" v-for="item of list" :to="'/detail/' + item.id" :key="item.id">
          <img :src="item.imgUrl" class="item-img" :key="item.id"/>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
  export default {
    name: 'HomeRecommend',
    props: {
      list: Array
    }
  }
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title
    line-height: .8rem
    background: #eee
    text-indent: .2rem
    margin-top: .2rem
  .item
    display: flex
    height: 1.9rem
    overflow: hidden
    border-bottom: 1px solid #eee
    &:last-child
      border-bottom: none
    .item-img
      width: 1.7rem
      height: 1.7rem
      padding: 0.1rem
    .item-info
      flex: 1
      padding: .1rem
      min-width: 0
      .item-title
        line-height: .54rem
        font-size: .32rem
        ellipsis()
      .item-desc
        line-height: .4rem
        color: #ccc
        font-size: .25rem
        ellipsis()
      .item-button
        margin-top: .16rem
        color: #fff
        background: #ff9300
        padding: 0 .2rem
        line-height: .5rem
        border-radius: .06rem
        
</style>