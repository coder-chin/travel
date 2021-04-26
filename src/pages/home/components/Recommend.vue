<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of list" :key="item.id">
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
  props: {
    list: Array
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