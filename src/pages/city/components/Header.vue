<template>
  <div class="header">
    <router-link to="/">
      <div class="iconfont back-home">&#xe624;</div>
    </router-link>
    <div class="header-title">
      <span>选择城市</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'cityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variable.styl'

  .header
    height: $headerHeight
    line-height: $headerHeight
    .back-home
      color: #fff
      float left
      width: .64rem
      text-align: center
      font-size: .4rem
    .header-title
      // line-height: $headerHeight
      // height: $headerHeight
      background: $bgColor
      text-align: center
      color: #fff
      font-size : .36rem
</style>
