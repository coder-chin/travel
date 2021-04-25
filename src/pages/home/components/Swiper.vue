<template>
  <div>
     <swiper :options="swiperOption" class="swiper">
    <!-- slides -->
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img :src="item.imgUrl" alt="">
      </swiper-slide>
    
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data() {
    return{
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
      },
      swiperList: [
        {
          id: '001',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1802/42/7c92b9a381e46402.jpg_640x200_1cdce2a4.jpg'
        },
        {
          id: '002',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1801/1a/94428c6dea109402.jpg_640x200_2cf590d8.jpg'
        }
      ]
    }
  }
}
</script>

<style lang='less' scoped>
  /deep/ .swiper-pagination-bullet-active  // .wrapper >>> .swiper-pagination-bullet-active
  {
    background-color: #fff;
  }
  .swiper{
    width: 100%;
    height: 31.25vw;  //如果不给swiper设置高度，会产生抖动
    img{
    width: 100%;
    }
    
  }
  
</style>