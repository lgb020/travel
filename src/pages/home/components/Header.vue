<template>
	<div class="header">
		<div class="header-left">
		<div class="iconfont back-icon">&#xe624;</div>
		</div>
		<div class="header-input"><span class="iconfont search-icon">&#xe632;</span>输入城市景点游玩主题</div>
		<router-link to='/city'>
		  <div class="header-right">{{this.city}}<span class="iconfont arrow-icon">&#xe65e;</span></div>
		</router-link>
	</div>
</template>

<script>
  import { mapState } from 'vuex'
	export default {
		name: 'HomeHeader',
		computed: {
		  ...mapState(['city'])
		}
	}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    display: flex
    line-height: .86rem
    background: $bgColor
    color: #fff
    .header-left
      width: .64rem
      float: left
				.back-icon
					text-align: center
					font-size: .4rem
    .header-input
      flex: 1
      margin-top: .12rem
      margin-left: .2rem
      padding-left: .2rem
      line-height: .64rem
      background: #fff
      border-radius: .1rem
      color: #ccc
      height: .64rem
				.search-icon
          margin-right :.1rem
    .header-right
      min-width: 1.04rem
      padding: 0 .1rem
      float: right
      text-align: center
      color: #fff
      .arrow-icon
        font-size: .24rem
</style>