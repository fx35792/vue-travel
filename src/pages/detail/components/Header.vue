<template>
  <div>
    <router-link tag="div" to="/" class="header-abs" v-show="showAbs">
      <div class="iconfont header-abs-icon">&#xe696;</div>
    </router-link>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
      <router-link to="/">
        <div class="iconfont header-fixed-icon">&#xe696;</div>
      </router-link>景点详情
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.header-abs {
  position: absolute;
  z-index: 2;
  top: 0.2rem;
  left: 0.2rem;
  width: 0.8rem;
  height: 0.8rem;
  line-height: 0.8rem;
  border-radius: 50%;
  text-align: center;
  background: rgba(0, 0, 0, 0.8);

  .header-abs-icon {
    color: #fff;
    font-size: 0.46rem;
  }
}

.header-fixed {
  position: fixed;
  z-index: 999;
  top: 0;
  left: 0;
  right: 0;
  height: $headHeight;
  line-height: $headHeight;
  background: $bgColor;
  text-align: center;
  color: #fff;
  font-size: 0.32rem;

  .header-fixed-icon {
    position: absolute;
    top: 0;
    left: 0;
    width: 0.64rem;
    text-align: center;
    font-size: 0.4rem;
    color: #fff;
  }
}
</style>
