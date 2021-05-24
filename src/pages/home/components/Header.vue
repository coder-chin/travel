<template>
  <div class="header">
    <div class="header-left">
      <i class='iconfont'>&#xe624;</i>
    </div>
    <div class="header-input">
      <i class='iconfont'>&#xe632;</i>
      输入城市/景点/游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{this.city}}
        <i class="iconfont">&#xe6aa;</i>
      </div>
    </router-link>
  </div>
</template>

<script>
import {mapState} from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState(['city'])
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
      min-width: 1.04rem;
      padding: 0 .1rem;
      float: right;
      color: #fff;
      text-align: center;
      i{
        font-size: .3rem;
        margin-left: -0.06rem;
      }
    }
  }
</style>