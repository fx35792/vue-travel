<template>
  <div class="container" @click="handleCloseGallery">
    <div class="wrapper">
      <swiper :options="swiperOption">
        <swiper-slide v-for="(item,index) in imgs" :key="index">
          <img :src="item" class="gallery-img">
        </swiper-slide>
        <div class="swiper-pagination" slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CommomGallery',
  props: {
    imgs: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observeParents: true,
        observer: true,
        autoplay: false
      }
    }
  },
  methods: {
    handleCloseGallery () {
      this.$emit('close')
    }
  }
}
</script>

<style lang="stylus" scoped>
.container >>> .swiper-container {
  overflow: inherit;
}

.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  position: fixed;
  z-index: 999;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  background: #000;
  color: #fff;

  .wrapper {
    height: 0;
    width: 100%;
    padding-bottom: 100%;

    .gallery-img {
      width: 100%;
    }

    .swiper-pagination {
      bottom: -1rem;
    }
  }
}
</style>
