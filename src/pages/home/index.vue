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
        <swiper-item v-for="item in swiperdata" :key="item.goods_id">
          <img :src="item.image_src" alt />
        </swiper-item>
      </block>
    </swiper>

    <!-- 分类 -->
    <div class="categories">
      <img v-for="item in catitems" :key="item.name" :src="item.image_src" alt />
    </div>

    <!-- 楼层 -->
    <ul class="floor">
      <li v-for="(item,index) in floordata" :key="index">
        <img :src="item.floor_title.image_src" alt />
        <div class="product-list">
          <img :src="item.product_list[0].image_src" alt />
          <div class="right">
            <block v-for="(item1,index1) in item.product_list" :key="item1.name">
              <img v-if="index1" :src="item1.image_src" alt />
            </block>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      //轮播图数据
      swiperdata: [],
      //分类列表
      catitems: [],
      //楼层列表
      floordata: []
    };
  },
  //页面第一次加载就写在这里
  onLoad() {
    //调用轮播图
    this.getSwiperdata();
    //调用分类列表
    this.getCatitems();
    //调用楼层列表
    this.getFloordata();
  },
  methods: {
    //请求轮播图数据
    getSwiperdata() {
      this.$request({
        url: "/api/public/v1/home/swiperdata"
      }).then(data => {
        // console.log(data);
        this.swiperdata = data.data.message;
      });
    },
    //请求分类列表
    getCatitems() {
      this.$request({
        url: "/api/public/v1/home/catitems"
      }).then(data => {
        // console.log(data);
        this.catitems = data.data.message;
      });
    },
    //请求楼层数据
    getFloordata() {
      this.$request({
        url: "/api/public/v1/home/floordata"
      }).then(data => {
        console.log(data);
        this.floordata = data.data.message;
      });
    }
  }
};
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