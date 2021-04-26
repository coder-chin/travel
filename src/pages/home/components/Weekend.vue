<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item of weekendList" :key="item.id">
        <div class="img-wrapper">
          <img :src="item.imgUrl" alt="">
        </div>
        
        <div class='info'>
          <p class='item-title'>{{item.title}}</p>
          <p class='item-desc'>{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data() {
    return {
      "weekendList":[{
        "id": "0001",
        "imgUrl": "http://img1.qunarzz.com/sight/source/1510/6e/1ea71e2f04e.jpg_r_640x214_aa6f091d.jpg",
        "title": "北京温泉排行榜",
        "desc": "细数北京温泉，温暖你的冬天"
      }, {
        "id": "0002",
        "imgUrl": "http://img1.qunarzz.com/sight/source/1505/aa/7baaf8a851d221.jpg_r_640x214_1431200f.jpg",
        "title": "北京必游TOP10",
        "desc": "来北京必去的景点非这些地方莫属"
      }, {
        "id": "0003",
        "imgUrl": "http://img1.qunarzz.com/sight/source/1505/9e/21df651e19af5d.jpg_r_640x214_3ea5bb38.jpg",
        "title": "寻找北京的皇城范儿",
        "desc": "数百年的宫廷庙宇，至今依旧威严霸气"
      }
      ]
    }
  }
}
</script>

<style lang="less" scoped>
  .title{
    height: .6rem;
    line-height: .6rem;
    background-color: #eee;
    text-indent: .2rem;
    margin-top: .2rem;
    font-size: .3rem;
  }
  .img-wrapper{
    width: 100%;
    height: 0;
    padding-bottom: 33.9%;
    overflow: hidden;
    img{
      width: 100%;
    }
  }
  .info{
    padding: .1rem;
    .item-title{
      line-height: .54rem;
      font-size: .32rem;
    }
    .item-desc{
      line-height: .4rem;
      color: #ccc;
    }
  }

</style>