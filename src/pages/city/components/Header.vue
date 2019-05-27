<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <div class="iconfont back-city">&#xe696;</div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header
  position relative
  height $headHeight
  line-height $headHeight
  background $bgColor
  text-align center
  color #ffffff
  .back-city
    position absolute
    left 0
    top 0
    width .64rem
    text-align center
    padding 0 .1rem
    font-size .48rem
    color #fff
</style>
