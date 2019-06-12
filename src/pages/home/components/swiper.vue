<template>
  <div class="wraper">
    <swiper :options="swiperOption" v-if="showSwiper">
    <!-- slides -->
    <swiper-slide v-for="item of swiperList" :key="item.id">
      <img class="swiper-img" :src="item.imgUrl">
    </swiper-slide>
    <!-- Optional controls -->
    <div class="swiper-pagination" slot="pagination"></div>
  </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: 3000
      },
    }
  },
  props: {
    swiperList: Array
  },
  computed: {
    showSwiper() {
      return this.swiperList.length
    }
  }
}
</script>
<style lang="stylus" scoped>
.wraper >>> .swiper-pagination-bullet-active
  background: #fff!important
.wraper
  width: 100%
  height: 0
  overflow: hidden
  padding-bottom: 32.25%
  background: #eee
  .swiper-img
    width: 100%
</style>
