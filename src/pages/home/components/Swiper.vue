<template>
  <div class="wrapper">
    <swiper :options="swiperOption" class='swiper'>
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
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '001',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1809/c6/2467595fffc3b302.jpg_750x200_cca13d51.jpg'
      }, {
        id: '002',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1809/69/8697f10f17f35a02.jpg_750x200_c98193a9.jpg'
      }, {
        id: '003',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1809/3b/7b654a05c9b61e02.jpg_750x200_eb04c4da.jpg'
      }, {
        id: '004',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1809/12/856f100069809e02.jpg_750x200_e3485a2b.jpg'
      }]
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
