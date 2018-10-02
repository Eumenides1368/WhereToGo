<template>
  <div>
    <div class="info">周末去哪儿玩</div>
    <div class="wrapper border-bottom" >
      <div v-for="item of weekList" :key="item.id">
        <img class="week-img" :src="item.imgUrl">
        <p class="week-location">{{ item.location }}</p>
        <p class="week-desc">{{ item.desc }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      weekList: [{
        id: '001',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/74/fd61f19f3f1cc1.jpg_r_640x214_6ebc0c51.jpg',
        location: '觅龙城的故事',
        desc: '两千多年历史的常州，道不尽悠悠历史'
      }, {
        id: '002',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/74/fd61f19f3f1cc1.jpg_r_640x214_6ebc0c51.jpg',
        location: '觅龙城的故事',
        desc: '两千多年历史的常州，道不尽悠悠历史'
      }, {
        id: '003',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/74/fd61f19f3f1cc1.jpg_r_640x214_6ebc0c51.jpg',
        location: '觅龙城的故事',
        desc: '两千多年历史的常州，道不尽悠悠历史'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variable.styl'
  .info
    width 100%
    height .6rem
    background #dddddd
    line-height .6rem
    margin-top .3rem
  .wrapper
    width 100%
    height 0
    padding-bottom .33rem
    .week-img
      width 100%
      height 40%
    .week-location
      font-size .3rem
      color #000000
      padding .1rem
    .week-desc
      font-size .24rem
      color #bbbbbb
      padding .1rem
</style>
