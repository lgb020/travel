<template>
  <div class="warpper">
    <swiper :options="swiperOption" v-if="showSwiper">
      <!-- slides -->
      <swiper-slide v-for="(item,index) of list" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" :key="item.id">
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
  export default {
    name: 'HomeSwiper',
    props: {
      list: Array
    },
    data () {
      return {
        swiperOption: {
          pagination: '.swiper-pagination',
          autoplay: 2000,
          loop: true
        }
      }
    },
    computed: {
      showSwiper () {
        return this.list.length
      }
    }
  }
</script>

<style lang="stylus" scoped>
  .warpper >>> .swiper-pagination-bullet-active
    background: #fff
  .warpper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 27%
    background: #eee
    .swiper-img
      width: 100%
</style>



