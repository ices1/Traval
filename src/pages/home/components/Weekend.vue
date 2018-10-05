<template>
  <div>
    <div class="weekend-title"> 周末去哪玩 </div>
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
  props: {
    weekendList: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .weekend-title
    background: #eee
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
