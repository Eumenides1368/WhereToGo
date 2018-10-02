<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <img class="item-img" :src="item.imgUrl">
        <div class="item-info">
          <p class="item-title">{{ item.title }}</p>
          <p class="item-desc">{{ item.desc }}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data: function () {
    return {
      recommendList: [{
        id: '001',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1807/c9/c9b31bce950940bda3.img.jpg_200x200_90c29e88.jpg',
        title: '常州中华恐龙园',
        desc: '常州中华恐龙园'
      }, {
        id: '002',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1807/c9/c9b31bce950940bda3.img.jpg_200x200_90c29e88.jpg',
        title: '常州中华恐龙园',
        desc: '常州中华恐龙园'
      }, {
        id: '003',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1807/c9/c9b31bce950940bda3.img.jpg_200x200_90c29e88.jpg',
        title: '常州中华恐龙园',
        desc: '常州中华恐龙园'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variable.styl'
  @import '~styles/mixins.styl'
  .title
    margin-top .2rem
    line-height .8rem
    background #eee
    text-indent .2rem
  .item
    overflow hidden
    display flex
    height 1.9rem
    .item-img
      height 1.7rem
      width 1.7rem
      padding .1rem
    .item-info
      flex 1
      padding .1rem
      min-width 0
      .item-title
        line-height .54rem
        font-size .32rem
        ellipsis()
      .item-desc
        line-height .4rem
        color #cccccc
        ellipsis()
      .item-button
        margin-top .2rem
        background #ff9300
        padding 0 .1rem
        border-radius .06rem
        color #ffffff
</style>
