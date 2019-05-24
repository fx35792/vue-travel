<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul class="item-list">
      <li class="item" v-for="item of list" :key="item.id">
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
