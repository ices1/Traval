<template> 
  <div class="search">
    <input type="text" class="search-input" placeholder="输入城市名或拼音">
  </div>
</template>

<script>
export default {
  name: 'citySearch'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variable.styl'

  .search
    height: .72rem
    padding: 0 .1rem
    background: $bgColor
    .search-input
      box-sizing: border-box
      height: .62rem
      line-height: .62rem
      text-align: center
      width: 100%
      border-radius: .1rem
      padding: 0 .1rem
</style>
