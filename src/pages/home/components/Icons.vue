<template>
  <div class="icons">
    <swiper>
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl">
          </div>
          <p class="icon-img-desc">{{ item.imgDesc }}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data: function () {
    return {
      imgList: [
        {
          id: '001',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          imgDesc: '热门景点'
        }, {
          id: '002',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          imgDesc: '网红top榜'
        }, {
          id: '003',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
          imgDesc: '动植物园'
        }, {
          id: '004',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
          imgDesc: '一日游'
        }, {
          id: '005',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
          imgDesc: '必有景点'
        }, {
          id: '006',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/ea/01d081dacb03cc02.png',
          imgDesc: '故都的秋'
        }, {
          id: '007',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/ea/01d081dacb03cc02.png',
          imgDesc: '恐龙园'
        }, {
          id: '008',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/50/26ffa31b56646402.png',
          imgDesc: '亲子游'
        }, {
          id: '009',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/75/eca3ce656c886502.png',
          imgDesc: '天目湖'
        }
      ]
    }
  },
  computed: {
    pages: function () {
      const pages = []
      this.imgList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/variable.styl'
  @import '~styles/mixins.styl'
  .icons >>> .swiper-container
    width 100%
    height 0
    padding-bottom 50%
  .icon
    float left
    width 25%
    height 0
    padding-bottom 25%
    position relative
    .icon-img
      position absolute
      top 0
      left 0
      right 0
      bottom .44rem
      box-sizing border-box
      padding .1rem
      .icon-img-content
        display block
        margin 0 auto
        height 100%
    .icon-img-desc
      display block
      position absolute
      left 0
      right 0
      bottom 0
      line-height .44rem
      height .44rem
      color $darkTextColor
      text-align center
      // 长文本显示...
      ellipsis()
</style>
