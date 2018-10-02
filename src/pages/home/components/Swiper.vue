<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" />
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data: function () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1809/bb/3796236479c84d02.jpg_750x200_57d68258.jpg'
      },
      {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1809/82/c94c9a77de17f902.jpg_750x200_a8419488.jpg'
      },
      {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1809/6a/847ac7b98f10e202.jpg_750x200_f0593cb5.jpg'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped >
  .wrapper >>> .swiper-pagination-bullet-active
      background white !important
      border .001rem solid #ccc
  .wrapper
    overflow hidden
    width 100%
    height 0
    padding-bottom 31.25%
    // 防止出现网速慢的情况下的网页抖动（就是没加载出来）
    .swiper-img
      width 100%
</style>
