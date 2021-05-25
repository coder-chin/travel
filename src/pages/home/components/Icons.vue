<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page,index) of pages" :key="index">
        <div class="icon" 
        v-for="item of page" :key="item.id">
          <img
          :src="item.imgUrl"
          />
          <p>{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: "HomeIcons",
  props: {
    list: Array
  },
  data() {
    return{
      swiperOption: {
        pagination: '.swiper-pagination',
        autoplay: false
      }
    }
  },
  computed: {
    pages() {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if(!pages[page])
          pages[page] = []
        pages[page].push(item)   //二维数组，自动分页
      })
      return pages
    }
  }
};
</script>

<style scoped lang='less'>
  /deep/ .swiper-container {
    width: 100%;
    height: 50vw;
  }
  .icon {
    width: 25%;
    float: left;
    height: 50%;
    box-sizing: border-box;
    text-align: center;
    padding-top: 0.2rem;
    img {
      width: 70%;
    }
    p{
      height: 0.4rem;
      line-height: .4rem;
      overflow: hidden;
      white-space: nowrap;
      text-overflow: ellipsis;
    }
  }
</style>