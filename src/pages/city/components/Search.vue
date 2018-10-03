<template>
  <div class="search">
    <input type="text" placeholder="请输入省份/城市名称" class="search-input">
  </div>
</template>

<script>
export default {
  name: 'CitySearch'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variable.styl'
  .search
    height .72rem
    background $bgColor
    padding 0 .1rem
    .search-input
      width 100%
      height .62rem
      padding 0 .1rem
      border-radius .06rem
      box-sizing border-box
      text-align center
      color #aaaaaa
</style>
