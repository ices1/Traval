<template>
  <div>
    <div class="recommend-title"> 热门推荐 </div>
    <div class="item border-bottom" v-for='item of recommendList' :key='item.id'>
      <img :src="item.imgUrl" alt="" class="item-img">
      <div class="item-info">
        <p class="item-title">{{item.title}}</p>
        <p class="item-desc">{{item.desc}}</p>
        <button class="item-btn">查看详情</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    recommendList: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .recommend-title
    background: #eee
    margin-top: .2rem
    text-indent: .2rem
    line-height: .8rem
  .item
    height: 2rem
    // margin: .1rem 0
    overflow: hidden
    display: flex
    // background: #ccc
    .item-info
      flex: 1
      padding: .1rem
      min-width: 0
    .item-img
      width: 2rem
      padding: .1rem
    .item-title
      line-height: .54rem
      font-size: .32rem
      ellipsis()
    .item-desc
      line-height: .4rem
      color: #bbb
      ellipsis()
    .item-btn
      margin-top: .16rem
      background: #ff9300
      border-radius: .06rem
      padding: 0 .2rem
      line-height: .44rem
      color: #fff
</style>
