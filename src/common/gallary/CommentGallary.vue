<template>
  <div class="container" @click="handleGallaryClick">
    <div class="warpper">
      <swiper :options="swiperOptions">
        <!-- slides -->
        <swiper-slide v-for="(item, index) in imgs" :key="index">
          <img class="gallary-img" :src="item">
        </swiper-slide>
        <!-- Optional controls -->
        <div class="swiper-pagination" slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'CommentGallary',
    props: {
      imgs: {
        type: Array,
        default () {
          return []
        }
      }
    },
    data () {
      return {
        swiperOptions: {
          autoplay: false,
          pagination: 'swiper-pagination',
          paginationType: 'fraction',
          observeParents: true,
          observer: true
        }
      }
    },
    methods: {
      handleGallaryClick () {
        this.$emit('close')
      }
    }
  }
</script>

<style lang="stylus" scoped>
  .container >>> .swiper-container
    overflow: inherit
  .container
    display: flex
    flex-direction: column
    justify-content: center
    position: fixed
    left: 0
    top: 0
    bottom: 0
    right: 0
    background: #000
    z-index: 99
    .warpper
      width: 100%
      height: 0
      padding-bottom: 100%
      .gallary-img
        width: 100%
        margin-top: 50%;
        transform: translateY(-50%);
      .swiper-pagination
        color: #fff
        bottom: -1rem
</style>