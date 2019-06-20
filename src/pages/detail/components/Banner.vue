<template>
  <div>
    <div class="banner" @click="handleClickBanner">
      <img
        src="https://img1.qunarzz.com/vs_ceph_vs_tts/559a05d5-3de7-4296-8d9d-c525259f38a8.jpg_r_640x420x90_2577f661.jpg"
        class="banner-img"
      >
      <div class="banner-info">
        <div class="banner-title">产品编号 639625298</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe653;</span>
          39
        </div>
      </div>
    </div>
    <common-gallery :imgs="bannerImgs" v-show="galleryStatus" @close="handleClickClose"></common-gallery>
  </div>
</template>

<script>
import CommonGallery from 'common/gallery/Gallery'
export default {
  name: 'DetailBanner',
  data () {
    return {
      galleryStatus: false,
      bannerImgs: [
        'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_r_800x800_6edd8174.jpg',
        'http://img1.qunarzz.com/sight/p55/201211/04/fbcab3e5d6479ce893835fbb.jpg_r_800x800_6360f514.jpg'
      ]
    }
  },
  methods: {
    handleClickBanner () {
      this.galleryStatus = true
    },
    handleClickClose () {
      this.galleryStatus = false
    }
  },
  components: {
    CommonGallery
  }
}
</script>

<style lang="stylus" scoped>
.banner {
  position: relative;
  overflow: hidden;
  height: 0;
  padding-bottom: 55%;

  .banner-img {
    width: 100%;
  }

  .banner-info {
    display: flex;
    position: absolute;
    right: 0;
    left: 0;
    bottom: 0;
    color: #fff;
    line-height: 0.6rem;
    background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8));

    .banner-title {
      flex: 1;
      font-size: 0.32rem;
      padding: 0 0.2rem;
    }

    .banner-number {
      height: 0.32rem;
      line-height: 0.32rem;
      margin-top: 0.14rem;
      padding: 0 0.4rem;
      border-radius: 0.2rem;
      background: rgba(0, 0, 0, 0.8);
      font-size: 0.24rem;

      .banner-icon {
        font-size: 0.24rem;
      }
    }
  }
}
</style>
