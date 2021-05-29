<template>
  <div class="list wrapper" ref="wrapper">
    <div>
      <!-- 当前城市 -->
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">{{this.currentCity}}</div>
          </div>
        </div>
      </div>
      <!-- 热门城市 -->
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper" 
              v-for="item of hot" 
              :key="item.id"
              @click='handleCityClick(item.name)'>
            <div class="button">{{ item.name }}</div>
          </div>
        </div>
      </div>
      <!-- 所有城市列表 -->
      <div class="area"
          v-for="(item, key) of cities"
          :key="key"
          :ref="key">
      <!-- 遍历对象  第一个参数是对象本身。第二个参数是对象名 -->
        <div class="title border-topbottom">{{ key }}</div>
        <div class="item-list">
          <div
            class="item border-bottom"
            v-for="innerItem of item"
            :key="innerItem.id"
            @click='handleCityClick(innerItem.name)'
          >
            {{ innerItem.name }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from "better-scroll";
import { mapState } from 'vuex'
export default {
  name: "CityList",
  props: {
    hot: Array,
    cities: Object,
    letter: String,
  },
  mounted() {
    this.scroll = new Bscroll(this.$refs.wrapper);
  },
  watch: {
    letter() {
      if (this.letter) {
        const element = this.$refs[this.letter][0]   //为什么获取到的是数组?因为ref为该字母的可能有很多
        //如果属性名是一个变量，可以这样写obj[variable]
        this.scroll.scrollToElement(element);
        //定位到该DOM
      }
    },
  },
  methods: {
    handleCityClick(city){
      this.$store.commit('changeCity',city)
      this.$router.push('/')
    }
  },
  computed: {
    ...mapState({
      currentCity: 'city'
    })
  }
};
</script>

<style lang="less" scoped>
.border-topbottom {
  &:before {
    border-color: #ccc;
  }
  &:after {
    border-color: #ccc;
  }
}
.border-bottom {
  &:before {
    border-color: #ccc;
  }
}
.list {
  position: absolute;
  overflow: hidden;
  top: 1.58rem;
  left: 0;
  right: 0;
  bottom: 0;
  .title {
    line-height: 0.54rem;
    background: #eee;
    padding-left: 0.2rem;
    color: #666;
    font-size: 0.26rem;
  }
  .button-list {
    padding: 0.1rem 0.6rem 0.1rem 0.1rem;
    overflow: hidden;
    .button-wrapper {
      width: 33.33%;
      float: left;
      .button {
        text-align: center;
        margin: 0.1rem;
        padding: 0.1rem 0;
        border-radius: 0.06rem;
        border: 0.02rem solid #ccc;
      }
    }
  }
  .item-list {
    .item {
      line-height: 0.76rem;
      padding-left: 0.2rem;
    }
  }
}
</style>