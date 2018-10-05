<template>
  <div>
    <div
      class="item"
      v-for="(item, index) in list"
      :key="index"
    >
      <div class="item-title border-bottom">
        <span class="item-title-icon"></span>
        <div class="item-content">{{ item.title }}</div>
      </div>
      <div v-if="item.children" class="item-children">
        <detail-list :list="item.children"></detail-list>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variable.styl'
  .item-title
    line-height .8rem
    font-size .32rem
    padding 0 .2rem
    .item-title-icon
      display: inline-block
      position: absolute
      width: .36rem
      height: .36rem
      top: .26rem
      left: .2rem
      background: url(//s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat
      margin-right: .1rem
      background-size: .4rem 3rem
    .item-content
      margin-left .4rem
  .item-children
    padding 0 .2rem
</style>
