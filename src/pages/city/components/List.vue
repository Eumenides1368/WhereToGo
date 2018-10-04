<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area border-topbottom">
        <div class="title">您的位置</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">{{ this.currentCity }}</div>
          </div>
        </div>
      </div>
      <div class="area border-topbottom">
        <div class="title">热门城市</div>
        <div class="content">
          <div class="button-list">
            <div class="button-wrapper" v-for="item of hot" :key="item.id">
              <div class="button" @click="handleCity(item.name)">{{ item.name }}</div>
            </div>
          </div>
        </div>
      </div>
      <div
        class="area border-topbottom"
        v-for="(item, key) of cities"
        :key="key"
        :ref="key">
        <div class="title">{{ key }}</div>
        <div class="item-list">
          <div class="item border-bottom"
            v-for="innerItem of item"
            :key="innerItem.id"
            @click="handleCity(innerItem.name)"
          >
            {{ innerItem.name }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
import { mapState, mapMutations } from 'vuex'
export default {
  name: 'CityList',
  props: {
    hot: Array,
    cities: Object,
    letter: String
  },
  computed: {
    ...mapState({
      currentCity: 'city'
    })
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  },
  methods: {
    handleCity (city) {
      // this.$store.commit('changeCity', city)
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variable.styl'
  .border-topbottom
    &:before
      color #cccccc
    &:after
      color #cccccc
  .border-bottom
    &:before
      color #cccccc
  // .area
  //   height .44rem
  //   background #eeeeee
  .list
    overflow hidden
    position absolute
    top 1.58rem
    left 0
    right 0
    bottom 0
  .title
    background #eeeeee
    padding-left .1rem
    color #777777
    line-height .44rem
    font-size .26rem
  .button-list
    padding .1rem .6rem .1rem .1rem
    overflow hidden
    .button-wrapper
      width 33.33%
      float left
      .button
        margin .1rem
        padding .1rem 0
        text-align center
        border .02rem solid #cccccc
        border-radius .06rem
  .item-list
    .item
      padding-left .2rem
      height .64rem
      line-height .64rem
</style>
