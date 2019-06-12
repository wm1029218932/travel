<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl" alt="">
            <p class="icon-title">{{item.desc}}</p>
          </div>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      swiperOption: {
        autoplay: false
      },
      iconList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        desc: '景点门票'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/3e/86314b2af03b7502.png',
        desc: '水上乐园'
      }, {
        id: '0003',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/3ef092d0a89ffddb7f781cda30c8ae49.png',
        desc: '魔都上海'
      }, {
        id: '0004',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        desc: '景点门票'
      }, {
        id: '0005',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/3e/86314b2af03b7502.png',
        desc: '水上乐园'
      }, {
        id: '0006',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/3ef092d0a89ffddb7f781cda30c8ae49.png',
        desc: '魔都上海'
      }, {
        id: '0007',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        desc: '景点门票'
      }, {
        id: '0008',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/3e/86314b2af03b7502.png',
        desc: '水上乐园'
      }]
    }
  },
  computed: {
    // 给图标分页
    pages() {
      let pages = [];
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if(!pages[page]){
          pages[page] = [];
        }
        pages[page].push(item)
      })
      return pages
    },
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl'; // @表示src目录，在css中使用@前面需要加~线
@import '~styles/mixins.styl';
.icons >>> .swiper-container
  width: 100%
  height: 0
  padding-bottom: 50%
.icon
  width: 25%
  height: 0
  float: left
  padding-bottom: 25%
  overflow: hidden
  position: relative
  .icon-img
    position: absolute
    left: 0
    top: 0
    right: 0
    bottom: 0.44rem
    padding-top: .1rem
    text-align: center
    .icon-img-content
      width: 1.1rem
      height: 1.1rem
    .icon-title
      ellipsis()
      margin-top: .1rem
</style>
