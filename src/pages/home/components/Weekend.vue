<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul class="item-list">
      <li class="item" v-for="item of recommendList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" alt="">
        </div>
        <div class="item-info">
          <div class="item-title">{{item.title}}</div>
          <div class="item-desc">{{item.desc}}</div>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1603/6d/2f67ae0659f41f.jpg_r_640x214_bf6cbd0b.jpg',
        title: '北京赏花好地方北京赏花好地方北京赏花好地方',
        desc: '乱花渐欲迷人眼，京城赏花大搜索乱花渐欲迷人眼，京城赏花大搜索乱花渐欲迷人眼，京城赏花大搜索'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1603/6d/2f67ae0659f41f.jpg_r_640x214_bf6cbd0b.jpg',
        title: '京城周末撒欢',
        desc: '在帝都过周末，不仅仅是城中游！'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1603/6d/2f67ae0659f41f.jpg_r_640x214_bf6cbd0b.jpg',
        title: '京城溜娃必去',
        desc: '德智体美劳全面发展的亲子日，这些地方该去看看'
      }]
    }
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/mixins.styl';
.title
  margin-top .1rem
  line-height .8rem
  background #eeeeee
  text-indent .2rem
.item-list
  .item
      position relative;
      overflow hidden;
      padding 0 0 .2rem;
    .item-img-wrapper
      overflow hidden
      img
        width 100%
        height 100%
    .item-info
      overflow hidden
      padding-left .22rem
      .item-title
        margin-top .26rem
        height .44rem;
        color #212121;
        font-size .32rem;
        line-height .44rem
        ellipsis()
      .item-desc
        margin-top .1rem
        height .34rem
        line-height .34rem
        vertical-align text-bottom
        color #616161
        font-size .24rem
        ellipsis()
</style>
