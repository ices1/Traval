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
  data () {
    return {
      recommendList: [{
        id: '001',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1603/c5/c5e2b211d10d4bb90.img.jpg_200x200_2a971b62.jpg',
        title: '西溪国家湿地公园',
        desc: '千岛湖天迹热气球球气热迹天湖岛千'
      }, {
        id: '002',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1505/c6/c6596631d2c78cda.water.jpg_200x200_4c3a7a9a.jpg',
        title: '千岛湖夜游',
        desc: '千岛湖夜游游夜湖岛千'
      }, {
        id: '003',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1603/ae/aecef86d7655873f90.water.jpg_200x200_22a0790e.jpg',
        title: '杭州野生动物世界',
        desc: '杭州野生动物世界界世物动生野州杭'
      }]
    }
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
