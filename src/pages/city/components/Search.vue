<template>
  <div class="search">
    <input type="text" placeholder="输入城市名或拼音" class="search-input">
  </div>
</template>

<script>
export default {
  name: 'CitySearch',
}
</script>

<style lang="less" scoped>
  .search{
    height: .72rem;
    background-color: #00bcd4;
    padding: 0 .1rem;
    input{
      box-sizing: border-box;
      height: .62rem;
      line-height: .62rem;
      width: 100%;
      text-align: center;
      border-radius: .1rem;
      color: #666;
      padding: 0 .2rem;
    }
  }
</style>