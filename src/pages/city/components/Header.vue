<template>
  <div class="header">
    <router-link to="/">
      <div class="iconfont">&#xe624;</div>
    </router-link>
    城市选择
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
@import '~styles/variable.styl'
  .header
    position relative
    overflow hidden
    height $headerHeight
    line-height $headerHeight
    text-align center
    color #ffffff
    background $bgColor
    font-size .32rem
    .iconfont
      position absolute
      top 0
      left 0
      width .64rem
      font-size .4rem
      color #ffffff
</style>
