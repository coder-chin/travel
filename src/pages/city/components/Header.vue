<template>
  <div class='header'>
    <router-link to="/">
      <i class='iconfont back'>&#xe624;</i>
    </router-link>
    城市选择
  </div>
</template>
<script>
export default {
  name: "CityHeader",
}
</script>

<style lang="less" scoped>
  .header{
    height: .86rem;
    line-height: .86rem;
    text-align: center;
    font-size: .32rem;
    color: #fff;
    font-weight: 600;
    background-color: #00bcd4;
    position: relative;
    .back{
      width: .64rem;
      text-align: center;
      font-size: .4rem;
      position: absolute;
      top: 0;
      left: 0;
      color: #fff;
    }
  }
</style>