<template>
  <div>
    <div class="title">热门推荐</div>
    <ul class="item-list">
      <li class="item border-bottom" v-for="item of list" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" alt="">
        </div>
        <div class="item-info">
          <div class="item-title">{{item.title}}</div>
          <div class="item-desc">{{item.desc}}</div>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
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
  margin-left .24rem
  .item
      position relative;
      overflow hidden;
      padding .2rem 0;
    .item-img-wrapper
      width 2rem
      height 2rem
      float left
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
        margin-top .14rem
        height .34rem
        line-height .34rem
        vertical-align text-bottom
        color #616161
        font-size .24rem
      .item-button
        margin-top .22rem
        border-radius .03rem
        padding .08rem .2rem
        background #ff9300
        font-size .24rem
        color #fff
</style>
