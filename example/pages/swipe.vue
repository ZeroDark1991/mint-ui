<template>
  <div class="page-swipe">
    <h1 class="page-title">Swipe</h1>
    <p class="page-swipe-desc">基础用法</p>
    <mt-swipe :auto="4000">
      <mt-swipe-item class="slide1">1</mt-swipe-item>
      <mt-swipe-item class="slide2">2</mt-swipe-item>
      <mt-swipe-item class="slide3">3</mt-swipe-item>
    </mt-swipe>

    <p class="page-swipe-desc">隐藏 indicators</p>
    <mt-swipe :show-indicators="false">
      <mt-swipe-item class="slide1">1</mt-swipe-item>
      <mt-swipe-item class="slide2">2</mt-swipe-item>
      <mt-swipe-item class="slide3">3</mt-swipe-item>
    </mt-swipe>
    <p>{{index}}</p>
    <p class="page-swipe-desc">取消自动播放</p>
    <button @click="handleJump(1)">goto</button>
    <mt-swipe ref="test" :auto="0" :continuous="false" :prevEnd="prevEnd" @change="handleChange">
      <mt-swipe-item class="slide1">1</mt-swipe-item>
      <mt-swipe-item class="slide2">2</mt-swipe-item>
      <mt-swipe-item class="slide3">3</mt-swipe-item>
    </mt-swipe>

    <p class="page-swipe-desc">设置默认显示页</p>
    <mt-swipe :auto="0" :defaultIndex="1">
      <mt-swipe-item class="slide1">1</mt-swipe-item>
      <mt-swipe-item class="slide2">2</mt-swipe-item>
      <mt-swipe-item class="slide3">3</mt-swipe-item>
    </mt-swipe>

    <p class="page-swipe-desc">单个幻灯片</p>
    <mt-swipe :show-indicators="false">
      <mt-swipe-item class="slide1">SINGLE SLIDE</mt-swipe-item>
    </mt-swipe>
  </div>
</template>
<script>
export default {
  data() {
    return {
      index: 1
    };
  },
  methods: {
    prevEnd() {
      console.log('end !!!');
    },
    handleChange(index) {
      console.log(index);
      this.index = index;
    },
    handleJump(index) {
      this.$refs.test.jumpToIndex(index);
    }
  }
};
</script>
<style>
  @component-namespace page {
    @component swipe {
      @descendent desc {
        text-align: center;
        color: #666;
        margin-bottom: 5px;
      }
      .mint-swipe {
        height: 200px;
        color: #fff;
        font-size: 30px;
        text-align: center;
        margin-bottom: 20px;
      }

      .mint-swipe-item {
        line-height: 200px;
      }

      .slide1 {
        background-color: #0089dc;
        color: #fff;
      }

      .slide2 {
        background-color: #ffd705;
        color: #000;
      }

      .slide3 {
        background-color: #ff2d4b;
        color: #fff;
      }
    }
  }
</style>
