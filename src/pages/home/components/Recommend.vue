<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <img :src="item.imgUrl" alt="">
        <div class='info'>
          <p class='item-title'>{{item.title}}</p>
          <p class='item-desc'>{{item.desc}}</p>
          <button>查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data() {
    return {
      "recommendList": [
        {
        "id": "0001",
        "imgUrl": "http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_140x140_80f63803.jpg",
        "title": "故宫",
        "desc": "东方宫殿建筑代表，世界宫殿建筑典范"
        }, 
        {
        "id": "0002",
        "imgUrl": "http://img1.qunarzz.com/sight/p0/1511/d2/d2aec2dfc5aa771290.water.jpg_140x140_abb362a7.jpg",
        "title": "南山滑雪场",
        "desc": "北京专业级滑雪圣地"
        }, 
        {
        "id": "0003",
        "imgUrl": "http://img1.qunarzz.com/sight/p0/1501/f4/f467729126949c3a.water.jpg_140x140_ef235b1c.jpg",
        "title": "天安门广场",
        "desc": "我爱北京天安门，天安门上太阳升"
        }
      ],
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
  .item{
    display: flex;
    height: 1.9rem;
    img{
      width: 1.7rem;
      height: 1.7rem;
      padding: .1rem;
    }
    .info{
      flex: 1;
      min-width: 0;
      padding: .1rem;
      .item-title{
        line-height: .54rem;
        font-size: .32rem;
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis;
      }
      .item-desc{
        height: .4rem;
        line-height: .4rem;
        color: #ccc;
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis;
      }
      button{
        background-color: #ff9300;
        border-radius: .06rem;
        margin-top: .2rem;
        padding: 0 .1rem;
        color: #fff;
        font-weight: 600;
      }
    }
  }
</style>