<template>
  <div class="header">
    <div class="header-left">
      <i class='iconfont'>&#xe624;</i>
    </div>
    <div class="header-input">
      <i class='iconfont'>&#xe632;</i>
      输入城市/景点/游玩主题
    </div>
    <div class="header-right">
      {{this.city}}
      <i class="iconfont">&#xe6aa;</i>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String,
  }
}
</script>

<style lang='less' scoped>
  .header{
    height: .86rem;
    display: flex;
    background-color: #00bcd4;
    color: #fff;
    height: .86rem;
    line-height: .86rem;
    .header-left{
      width: .64rem;
      float: left;
      i{
        font-size: .4rem;
        display: inline-block;
        margin: 0 .06rem;
      }
    }
    .header-input{
      flex: 1;  //自动撑开
      background: #fff;
      border-radius: .1rem;
      margin: .12rem .2rem;
      height: .62rem;
      line-height: .62rem;
      color: #ccc;
      padding-left: .07rem;
    }
    .header-right{
      width: 1.24rem;
      float: right;
      text-align: center;
      i{
        font-size: .3rem;
        margin-left: -0.06rem;
      }
    }
  }
</style>