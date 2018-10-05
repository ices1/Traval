<template>
  <div class="wrapper">
    <swiper :options="swiperOption" class='swiper' v-if='loadlist'>
      <!-- slides -->
      <swiper-slide v-for='item of swiperList' :key='item.id'>
        <img class='swiper-img' :src='item.imgUrl' alt=''>
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default{
  name: 'HomeSwiper',
  props: {
    swiperList: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      }
    }
  },
  computed: {
    loadlist () {
      // console.log('两次获取 swiperList', this.swiperList.length)
      return this.swiperList.length
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background-color: #fff !important
  .wrapper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 26.7%
    background-color #ddd
    // width: 100%
    // heigit: 26.7vw
    .swiper-img
      width: 100%
</style>
