<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe696;</div>
    </div>
    <div class="header-content">
      <span class="iconfont search-icon">&#xe609;</span>
      输入城市/景点/游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{this.city}}
        <span class="iconfont arrow-icon">&#xe6aa;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl';
.header
  display flex
  background $bgColor
  color #fff
  height .88rem
  line-height .88rem
  .header-left
    float left
    width .64rem
    text-align center
    padding 0 .1rem
    .back-icon
      font-size .48rem
  .header-content
    flex 1
    margin-top .1rem
    height .68rem
    line-height .68rem
    background #ffffff
    border-radius .05rem
    color #e4e7ea
    .search-icon
      padding-left .2rem
  .header-right
    padding 0 .22rem
    color #ffffff
</style>
