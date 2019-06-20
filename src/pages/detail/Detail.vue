<template>
  <div>
    <detail-banner :sightName="sightName" :bannerImg="bannerImg" :gallaryImgs="gallaryImgs"></detail-banner>
    <detail-header></detail-header>
    <div style="height:50rem">
      <detail-list :list="list"></detail-list>
    </div>
  </div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import axios from 'axios'
export default {
  name: 'Detail',
  data () {
    return {
      sightName: '',
      bannerImg: '',
      gallaryImgs: [],
      list: []
    }
  },
  methods: {
    getDetailInfo () {
      axios
        .get('/api/detail.json', {
          params: {
            id: this.$route.params.id
          }
        })
        .then(this.getDetailSucc)
    },
    getDetailSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        res = res.data
        this.sightName = res.sightName
        this.bannerImg = res.bannerImg
        this.gallaryImgs = res.gallaryImgs
        this.list = res.categoryList
      }
    }
  },
  mounted () {
    this.getDetailInfo()
  },
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  }
}
</script>

<style lang="stylus" scoped></style>
