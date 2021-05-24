<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img :src="bannerImg" alt=""
      class="banner-img">
      <div class="banner-info">
        <div class="banner-title">
          {{this.sightName}}
        </div>
        <div class="banner-number"><i class='iconfont banner-icon'>&#xe6de;</i>
        {{this.gallaryImgs.length}}
        </div>
      </div>
    </div>

    <common-gallary 
    :imgs="gallaryImgs" 
    v-show="showGallary"
    @close="handleGallaryClose"></common-gallary>
  </div>
</template>
  
  

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallary
  },
  props: {
    sightName:String,
    bannerImg:String,
    gallaryImgs:Array
  },
  data() {
    return {
      imgs: ['http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_600x330_bf9c4904.jpg',
      'http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_600x330_bf9c4904.jpg'],
      showGallary: false
    }
  },
  methods:  {
    handleBannerClick(){
      this.showGallary = true
    },
    handleGallaryClose(){
      this.showGallary = false
    }
  }
}
</script>

<style lang='less' scoped>
  .banner{
    overflow: hidden;
    position: relative;
    height: 0;
    padding-bottom: 55%;
    .banner-img{
      width: 100%;
    }
    .banner-info{
      display: flex;
      position: absolute;
      left: 0;
      right: 0;
      bottom: 0;
      line-height: .6rem;
      color: #fff;
      background-image: linear-gradient(top,rgba(0,0,0,0),rgba(0,0.0,.8));
      .banner-title{
        flex: 1;
        font-size: .32rem;
        padding: 0 .2rem;
      }
      .banner-number{
        height: .32rem;
        line-height: .4rem;
        border: .2rem;
        font-size: .24rem;
        background: rgba(0, 0, 0, .8); 
        padding: 0 .4rem;
        margin-top: .14rem;
        .banner-icon{
          font-size: .24rem;
        }
      }
    }
  }
</style>