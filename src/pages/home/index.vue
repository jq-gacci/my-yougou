<template>
  <div class="container">
    <div class="search-hotspot">
      <div>
        <icon type="search" size="18" color="#bbb"></icon>
        <span>搜索</span>
      </div>
    </div>
    <!-- 轮播图 -->
    <swiper
      indicator-dots
      autoplay
      circular
      indicator-active-color="#fff"
      indicator-color="rgba(255,255,255,0.3)"
    >
      <block>
        <swiper-item v-for="item in 5" :key="item">
          <img
            src="https://img11.360buyimg.com/n7/jfs/t1/43621/9/14397/72032/5d7890c5E1c52ae6a/cd4c27dde7f31073.jpg"
            alt
          />
        </swiper-item>
      </block>
    </swiper>

    <!-- 分类 -->
    <div class="categories">
      <img src="https://api.zbztb.cn/pyg/icon_index_nav_4@2x.png" alt />

      <img src="https://api.zbztb.cn/pyg/icon_index_nav_4@2x.png" alt />

      <img src="https://api.zbztb.cn/pyg/icon_index_nav_4@2x.png" alt />

      <img src="https://api.zbztb.cn/pyg/icon_index_nav_4@2x.png" alt />
    </div>

    <!-- 楼层 -->
    <ul class="floor">
      <li>
        <img src="https://api.zbztb.cn/pyg/pic_floor01_title.png" alt />
      </li>
      <div class="product-list">
        <img src="https://api.zbztb.cn/pyg/pic_floor01_1@2x.png" alt />
        <div class="right">
          <img src="https://api.zbztb.cn/pyg/pic_floor01_2@2x.png" alt />
          <img src="https://api.zbztb.cn/pyg/pic_floor01_2@2x.png" alt />
          <img src="https://api.zbztb.cn/pyg/pic_floor01_2@2x.png" alt />
          <img src="https://api.zbztb.cn/pyg/pic_floor01_2@2x.png" alt />
        </div>
      </div>
    </ul>
    <ul class="floor">
      <li>
        <img src="https://api.zbztb.cn/pyg/pic_floor01_title.png" alt />
      </li>
      <div class="product-list">
        <img src="https://api.zbztb.cn/pyg/pic_floor01_1@2x.png" alt />
        <div class="right">
          <img src="https://api.zbztb.cn/pyg/pic_floor01_2@2x.png" alt />
          <img src="https://api.zbztb.cn/pyg/pic_floor01_2@2x.png" alt />
          <img src="https://api.zbztb.cn/pyg/pic_floor01_2@2x.png" alt />
          <img src="https://api.zbztb.cn/pyg/pic_floor01_2@2x.png" alt />
        </div>
      </div>
    </ul>
    <ul class="floor">
      <li>
        <img src="https://api.zbztb.cn/pyg/pic_floor01_title.png" alt />
      </li>
      <div class="product-list">
        <img src="https://api.zbztb.cn/pyg/pic_floor01_1@2x.png" alt />
        <div class="right">
          <img src="https://api.zbztb.cn/pyg/pic_floor01_2@2x.png" alt />
          <img src="https://api.zbztb.cn/pyg/pic_floor01_2@2x.png" alt />
          <img src="https://api.zbztb.cn/pyg/pic_floor01_2@2x.png" alt />
          <img src="https://api.zbztb.cn/pyg/pic_floor01_2@2x.png" alt />
        </div>
      </div>
    </ul>
  </div>
</template>

<script>
export default {}
</script>

<style lang="less">
.search-hotspot {
  height: 100rpx;
  padding: 20rpx 16rpx;
  background-color: #eb4450;
  box-sizing: border-box;
  > div {
    background-color: #fff;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 60rpx;
    border-radius: 4rpx;
    color: #bbb;
    icon {
      margin: 8rpx 16rpx 0 0;
    }
  }
}
swiper {
  height: 340rpx;
  img {
    width: 100%;
    height: 100%;
  }
}
.categories {
  display: flex;
  height: 194rpx;
  justify-content: space-evenly;
  align-items: center;
  img {
    width: 128rpx;
    height: 140rpx;
  }
}
.floor {
  li {
    > img {
      height: 88rpx;
      width: 100%;
    }
  }
}
.product-list {
  padding: 20rpx 17rpx;
  display: flex;
  > img {
    width: 232rpx;
    height: 386rpx;
  }
  .right {
    flex: 1;
    font-size: 0;
    > img {
      width: 232rpx;
      height: 188rpx;
      margin: 0 0 10rpx 10rpx;
    }
  }
}
</style>