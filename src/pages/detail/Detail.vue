<template>
  <div>
    <detail-header></detail-header>
    <detail-banner></detail-banner>
    <div class="content">
      <detail-list :list="list"></detail-list>
    </div>
  </div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
export default {
  name: 'Detail',
  components: {
    DetailHeader: DetailHeader,
    DetailBanner: DetailBanner,
    DetailList: DetailList
  },
  data () {
    return {
      list: [{
        title: '成人票',
        children: [{
          title: '成人三馆联票',
          children: [{
            title: '成人三馆联票 - xx连锁店'
          }]
        }, {
          title: '成人五馆联票'
        }]
      }, {
        title: '学生票'
      }, {
        title: '儿童票'
      }, {
        title: '特殊票'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/variable.styl'
.content
  height 1000rem
</style>
