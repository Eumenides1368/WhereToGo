<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont">&#xe624;</span>
    </div>
    <div class="header-middle">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点
    </div>
    <router-link to="/city">
      <div class="header-right">
        <span class="iconfont">&#xe62d;</span>
        {{ this.city }}
      </div>
    </router-link>
  </div>
  <!-- 放在css里面的实在不知怎么注释 @import '~@/assets/styles/variable.styl' @表示src文件 -->
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState(['city'])
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variable.styl'
  .header
    line-height: .86rem
    background: $bgColor
    color #ffffff
    display flex
    .header-left
      width .64rem
      float left
      .iconfont
        margin-left .1rem
    .header-middle
      margin-top .12rem
      margin-left .1rem
      margin-right .12rem
      height .64rem
      line-height .64rem
      border-radius .1rem
      background #ffffff
      color #cccccc
      flex 1
      .iconfont
        margin-left .1rem
        margin-right .1rem
    .header-right
      min-width 1.04rem
      padding 0 .1rem
      text-align center
      padding-right .15rem
      color: #ffffff
      .iconfont
        font-size .2rem

</style>
