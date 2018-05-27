<template>
  <div class="header">
    城市选择
    <router-link to='/'>
      <div class="iconfont header-back">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    position: relative;
    overflow: hidden
    text-align: center
    color: #fff
    height: .86rem
    line-height: .86rem
    background: $bgColor
    font-size: .32rem;
    .header-back
      position: absolute;
      top: 0
      left: 0
      width: 0.64rem
      text-align: center
      font-size: .4rem;
      color: #fff
</style>