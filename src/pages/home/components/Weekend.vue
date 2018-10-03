<template>
  <div>
    <div class="weekend-title"> 热门推荐 </div>
    <div class="item border-bottom" v-for='item of weekendList' :key='item.id'>
      <div class="img-wrapper">
        <img :src="item.imgUrl" alt="" class="item-img">
      </div>
      <div class="item-info">
        <p class="item-title">{{item.title}}</p>
        <p class="item-desc">{{item.desc}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      weekendList: [{
        id: '001',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/9f/7d45cc38259e0.jpg_r_640x214_156f4299.jpg',
        title: '承载杭城的历史之地',
        desc: '承载杭城的历史之地地之史历的城杭载承'
      }, {
        id: '002',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/c1/1178c5696fcf57.jpg_r_640x214_a69542c6.jpg',
        title: '杭州江南古镇',
        desc: '杭州江南古镇镇古南江州杭'
      }, {
        id: '003',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/bc/83feb2e003d0dd.jpg_r_640x214_0b7269b8.jpg',
        title: '杭州多样乐园',
        desc: '这个周末终于可以陪宝贝去玩耍啦'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .weekend-title
    background: #eee
    margin-top: .2rem
    text-indent: .2rem
    line-height: .8rem
  // .item
  //   height: 2rem
  //   overflow: hidden
    .item-img
      width: 100%
      // height: 37.2%
      padding: .1rem 0
    .item-info
      padding: .05rem .05rem .2rem
      text-indent: .1rem
    .item-title
      line-height: .54rem
      font-size: .32rem
      ellipsis()
    .item-desc
      line-height: .4rem
      // color: #bbb
      font-size: .26rem
      ellipsis()
</style>
