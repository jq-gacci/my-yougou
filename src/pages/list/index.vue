<template>
  <div>
    <div class="header">
      <!-- 头部 -->
      <div class="search">
        <icon type="search" size="18"></icon>
        <input type="text" v-model="keyword" confirm-type="search" @confirm="reload" />
      </div>

      <!-- filter -->
      <ul class="nav">
        <li v-for="(item,index) in navArr"
            :key="item"
            @click="activeIndex=index"
            :class="{active:activeIndex===index}">{{item}}</li>
      </ul>
    </div>
    <!-- 商品列表 -->
    <ul class="goods-list">
      <li v-for="item in 5" :key="item">
        <img src="http://image2.suning.cn/uimg/b2c/newcatentries/0070078057-000000000634917020_1_800x800.jpg" alt="">
        <div class="right">
          <p class="goods-name text-line2">创维（Skyworth）55H9A 55英寸超薄 全面屏 4K超高清智能电视(黑色)</p>
          <p class="price">￥<span>129</span>.00</p>
        </div>
      </li>
    </ul>

    <!-- 提示没有数据了 -->
     <p class="tip"
       v-show="isLastPage">--我是有底线的--</p>
 
  </div>
</template>

<script>
export default {
data() {
  return {
      navArr: ["综合", "销量", "价格"],
  //搜索关键字
  keyword: "",
  activeIndex: 0,

   isLastPage: false,
  }
},
};
</script>

 <style lang="less">
.header {
  position: fixed;
  width: 100%;
  background-color: #fff;
  top: 0;
}
.search {
  height: 120rpx;
  padding: 0 16rpx;
  background-color: #eee;
  display: flex;
  align-items: center;
  position: relative;
  icon {
    position: absolute;
    top: 46rpx;
    left: 46rpx;
  }
  input {
    height: 60rpx;
    background-color: #fff;
    border-radius: 8rpx;
    width: 100%;
    font-size: 24rpx;
    padding-left: 76rpx;
  }
}
.nav {
  display: flex;
  justify-content: space-around;
  height: 100rpx;
  align-items: center;
  border: 1rpx solid #ddd;
  .active {
    color: #eb4450;
  }
}
.goods-list{
  margin-top: 220rpx;
  li{
    height: 262rpx;
    border-bottom: 1rpx solid #ddd;
    display: flex;
    align-items: center;
    padding:0 20rpx;
    img{
      width: 200rpx;
      height: 200rpx;
      margin-right: 24rpx;
    }
    .right{
      flex: 1;
      display: flex;
      flex-direction: column;
    }
    .goods-name{
      font-size: 16px;
    }
    .price{
      color: #eb4450;
      font-size: 12px;
      margin-top: 54rpx;
    }
    span{
      font-size: 24px;
    }
  }
}
</style>