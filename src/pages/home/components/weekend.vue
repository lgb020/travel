<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item" v-for="item of list">
        <div class="item-img-warpper">
          <img :src="item.imgUrl" class="item-img" :key="item.id"/>
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: 'HomeWeekend',
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
  .item
    border-bottom: 1px solid #eee
    .item-img-warpper
      height: 0
      overflow: hidden
      padding-bottom: 37.1%;
      .item-img
        width: 100%
    .item-info
      padding: .1rem
      .item-title
        line-height: .54rem
        font-size: .28rem
        ellipsis()
      .item-desc
        line-height: .4rem
        color: #ccc
        font-size: .25rem
        ellipsis()
</style>