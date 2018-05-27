<template>
  <div class="warp">
    <div class="item" v-for="(item,index) of list" :key="index">
      <div class="item-title border-bottom">
        <span class="item-title-icon"></span>
        {{item.title}} <span class='price'>￥ 60</span>
      </div>
      <div v-if="item.children" class="item-children">
        <detail-list :list="item.children"></detail-list>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "DetailList",
    props: {
      list: Array
    }
  }
</script>

<style lang="stylus" scoped>
  .item-title-icon
    display: inline-block
    width: .36rem
    height: .36rem
    position: relative
    left: .06rem
    top: .06rem
    background: url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat
    margin-right: .1rem
    background-size: .4rem 3rem
  .item-title
    line-height: .8rem
    font-size: .32rem
    padding: 0 0 0 0.3rem
    position: relative;
    .price
      color: orange
      position: absolute;
      right: 0.4rem;
  .item-children
    padding: 0 0 0 .3rem
    background: none
</style>