<template>
  <div class="icons">
    <swiper>
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
  data () {
    return {
      iconList: [{
        id: '001',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        desc: '景点门票'
      }, {
        id: '002',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/17/99402a22ce4af302.png',
        desc: '一日游'
      }, {
        id: '003',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
        desc: '杭州必游'
      }, {
        id: '004',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
        desc: '动植物园'
      }, {
        id: '005',
        imgUrl: 'https://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
        desc: '网红Top榜'
      }, {
        id: '006',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/17/99402a22ce4af302.png',
        desc: '西湖'
      }, {
        id: '007',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png',
        desc: '杭州宋城'
      }, {
        id: '008',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/b8/c5dcdb58deec2402.png',
        desc: '西溪湿地'
      }, {
        id: '009',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/75/eca3ce656c886502.png',
        desc: '千岛湖'
      }, {
        id: '010',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/80/416c6ab3368d1f02.png',
        desc: '全部玩乐'
      }]
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
