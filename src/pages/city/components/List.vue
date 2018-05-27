<template>
  <div class="list" ref="warpper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-warpper">
            <div class="button">{{this.$store.state.city}}</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-warpper" v-for="item of hot" :key="item.id" @click="handleCityClick(item.name)">
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="area" v-for="(value,key) of cities" :key="key"  :ref="key">
        <div class="title border-topbottom">{{key}}</div>
        <div class="item-list">
          <div class="item border-bottom" v-for="innerItem of value" :key="innerItem.id" @click="handleCityClick(innerItem.name)">{{innerItem.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import Bscroll from 'better-scroll'
  export default {
    name: 'CityList',
    props: {
      hot: Array,
      cities: Object,
      letter: String
    },
    methods: {
      handleCityClick(city) {
        this.$store.commit('changeCity', city)
        this.$router.push('/')
      }
    },
    mounted () {
      this.scroll = new Bscroll(this.$refs.warpper)
    },
    watch: {
      letter () {
        if (this.letter) {
          const element = this.$refs[this.letter][0]
          this.scroll.scrollToElement(element)
        }
      }
    }
  }
  
</script>

<style lang="stylus" scoped>
  .border-topbottom
  &:before
    border-color: #ccc
  &:after
    border-color: #ccc
  .border-bottom
  &:before
    border-color: #ccc
  .list
    position: absolute
    top: 1.58rem
    left: 0
    right: 0
    bottom: 0
    overflow: hidden
    .title
      line-height: .54rem
      background: #eee
      padding-left: .2rem
      color: #666
      font-size: .26rem
    .button-list
      padding: .1rem .6rem .1rem .1rem
      overflow: hidden
      .button-warpper
        width: 33.33%
        float: left
        .button
          text-align: center
          padding: .1rem 0
          margin: .1rem
          border: .02rem solid #ccc
          border-radius: .08rem
    .item-list
      .item
        line-height: .76rem
        padding-left: .2rem
</style>