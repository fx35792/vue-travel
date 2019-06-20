<template>
  <div>
    <div class="title">热门推荐</div>
    <ul class="item-list">
      <router-link
        tag="li"
        class="item border-bottom"
        v-for="item of list"
        :key="item.id"
        :to="'/detail/'+item.id"
      >
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" alt>
        </div>
        <div class="item-info">
          <div class="item-title">{{item.title}}</div>
          <div class="item-desc">{{item.desc}}</div>
          <button class="item-button">查看详情</button>
        </div>
      </router-link>
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

.title {
  margin-top: 0.1rem;
  line-height: 0.8rem;
  background: #eeeeee;
  text-indent: 0.2rem;
}

.item-list {
  margin-left: 0.24rem;

  .item {
    position: relative;
    overflow: hidden;
    padding: 0.2rem 0;
  }

  .item-img-wrapper {
    width: 2rem;
    height: 2rem;
    float: left;
    overflow: hidden;

    img {
      width: 100%;
      height: 100%;
    }
  }

  .item-info {
    overflow: hidden;
    padding-left: 0.22rem;

    .item-title {
      margin-top: 0.26rem;
      height: 0.44rem;
      color: #212121;
      font-size: 0.32rem;
      line-height: 0.44rem;
      ellipsis();
    }

    .item-desc {
      margin-top: 0.14rem;
      height: 0.34rem;
      line-height: 0.34rem;
      vertical-align: text-bottom;
      color: #616161;
      font-size: 0.24rem;
    }

    .item-button {
      margin-top: 0.22rem;
      border-radius: 0.03rem;
      padding: 0.08rem 0.2rem;
      background: #ff9300;
      font-size: 0.24rem;
      color: #fff;
    }
  }
}
</style>
