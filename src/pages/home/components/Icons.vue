<template>
  <div class="icons">
    <swiper>
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
  data() {
    return {
      iconList: [
        {
          id: '001',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
          desc: '景点门票门票门票门票门票'
        },
        {
          id: '002',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
          desc: '滑雪季'
        },
        {
          id: '003',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
          desc: '滑雪季'
        },
        {
          id: '004',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
          desc: '滑雪季'
        },
        {
          id: '005',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
          desc: '滑雪季'
        },
        {
          id: '006',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
          desc: '滑雪季'
        },
        {
          id: '007',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
          desc: '滑雪季'
        },
        {
          id: '008',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
          desc: '滑雪季'
        },
        {
          id: '009',
          imgUrl: 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
          desc: '滑雪季'
        },
      ]
    }
  },
  computed: {
    pages() {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if(!pages[page])
        pages[page] = []
        pages[page].push(item)
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
      height: 0.28rem;
      line-height: .28rem;
  
      overflow: hidden;
      white-space: nowrap;
      text-overflow: ellipsis;
    }
  }
</style>