<template>
  <div>
     <swiper :options="swiperOption" class="swiper" v-if="list.length">
    <!-- slides -->
      <swiper-slide v-for="item of list" :key="item.id">
        <img :src="item.imgUrl" alt="">
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props:{
    list: Array
  },
  data() {
    return{
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
      }
    }
  }
}
</script>

<style lang='less' scoped>
  .swiper /deep/ .swiper-pagination-bullet-active 
  //.wrapper >>> .swiper-pagination-bullet-active
  {
    background-color: #fff !important;
  }
  .swiper{
    width: 100%;
    height: 31.25vw;  //如果不给swiper设置高度，会产生抖动
    img{
      width: 100%;
    }
  }
</style>