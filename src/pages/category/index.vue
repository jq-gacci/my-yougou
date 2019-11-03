<template>
  <div>
    <!-- 头部搜索 -->
    <TopBar></TopBar>
    <div class="main">
      <div class="left">
        <ul>
          <li
            v-for="(item,index) in 20"
            :key="index"
            @click="activeIndex=index"
            :class="{active:activeIndex===index}"
          >大家电</li>
        </ul>
      </div>
      <div class="right">
        <img src="../../../static/images/titleImage.png" alt="">
        <ul v-for="(item1, index1) in 4" :key="index1">
          <li class="cate2">
            <p class="title">/<span>电视</span>/</p>
            <ul>
              <li class="cate3" v-for="(item,index) in 9" :key="index">
                <img src="https://api.zbztb.cn/full/2fb113b32f7a2b161f5ee4096c319afedc3fd5a1.jpg" alt="">
                <p>曲面电视</p>
              </li>
            </ul>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import TopBar from "@/components/topbar";
export default {
  components: {
    TopBar
  },
  data() {
    return {
      activeIndex: 0
    };
  }
};
</script>

<style lang="less">
@red : #eb4450;
.main {
  display: flex;
  color: #333;
  position: absolute;
  top: 100rpx;
  left: 0;
  right: 0;
  bottom: 0;
  font-size: 14px;
}
.left {
  width: 198rpx;
  overflow: auto;
  li {
    height: 100rpx;
    background-color: #f4f4f4;
    border-bottom: 1rpx solid #eee;
    line-height: 100rpx;
    text-align: center;
    &.active {
      color: @red;
      background-color: #fff;
      position: relative;
      &::before {
        position: absolute;
        content: "";
        width: 8rpx;
        height: 60rpx;
        background-color: @red;
        left: 0;
        top: 20rpx;
      }
    }
  }
}
.right{
  flex:1;
  overflow: scroll;
  padding: 20rpx 16rpx;
  box-sizing: border-box;
  height: 100%;
  >img{
    width: 520rpx;
    height: 180rpx;
  }
  .title{
    height: 110rpx;
    color: #e0e0e0;
    text-align: center;
    line-height: 110rpx;

    span{
      color:#333;
      margin: 0 30rpx;
    }
  }
  .cate2>ul{
display: flex;
flex-wrap: wrap;
   .cate3{
     width: 33.33%;
text-align: center;
margin-top: 40rpx;
     img{
       width: 120rpx;
       height: 120rpx;
     }
   }
   p{
     margin-top: 14rpx;
   }
  }
}
</style>