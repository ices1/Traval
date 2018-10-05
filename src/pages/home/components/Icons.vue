<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for='(list, index) of pages' :key='index'>
        <div class="icon" v-for='item of list' :key='item.id'>
          <div class="icon-img">
            <img class='icon-img-content' :src='item.imgUrl' alt="">
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
    </swiper-slide>
  </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
    iconList: Array
  },
  data () {
    return {
      swiperOption: {
        autoplay: false
      }
    }
  },
  computed: {
    // pages 实现轮播分页，将 10 个 item 分为 一个二维数组，每一项 放 8个item
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variable.styl'
  @import '~styles/mixins.styl'
  .icons
    overflow: hidden
    // width: 100%
    height: 0
    padding-bottom: 50%
    // background-color green
    .icon
      position: relative
      float: left
      overflow: hidden
      width: 25%
      height: 0
      // background-color: red
      padding-bottom: 25%
      .icon-img
        position: absolute
        top: 0
        left: 0
        right: 0
        bottom: .44rem
        box-sizing: border-box
        padding: .1rem
        // background-color: blue
        .icon-img-content
          display: block
          margin: 0 auto
          height: 100%
      .icon-desc
        position: absolute
        left: 0
        right: 0
        bottom: 0
        text-align: center
        height: .44rem
        line-height: .44rem
        color: $darkTextColor
        ellipsis()
</style>
