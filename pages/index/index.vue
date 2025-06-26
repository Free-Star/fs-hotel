<template>
  <view class="page">
    <!-- Banner -->
    <swiper autoplay circular class="banner">
      <swiper-item v-for="(item, index) in banners" :key="index">
        <image :src="item" class="banner-image" />
      </swiper-item>
    </swiper>

    <!-- 推荐房源 -->
    <view class="recommend">
      <view class="title">推荐房源</view>
      <view class="list">
        <view class="card" v-for="(room, index) in recommends" :key="index" @click="toDetail(room)">
          <image :src="room.img" class="card-image" />
          <view class="card-name">{{ room.name }}</view>
          <view class="card-desc">{{ room.desc }}</view>
        </view>
      </view>
    </view>

    <button class="all-btn" @click="toList">查看全部房源</button>
  </view>
</template>

<script>
export default {
  data() {
    return {
      banners: [
        '/static/img/banner1.jpg',
        '/static/img/banner2.jpg',
        '/static/img/banner3.jpg'
      ],
      recommends: [
        { img: '/static/img/r1.jpg', name: '房源A', desc: '舒适大床房' },
        { img: '/static/img/r2.jpg', name: '房源B', desc: '海景套房' }
      ]
    }
  },
  methods: {
    toList() {
      uni.navigateTo({ url: '/pages/list/list' })
    },
    toDetail(room) {
      uni.navigateTo({ url: '/pages/detail/detail?name=' + room.name })
    }
  }
}
</script>

<style>
.banner {
  height: 200rpx;
}
.banner-image {
  width: 100%;
  height: 200rpx;
}
.recommend {
  padding: 20rpx;
}
.title {
  font-weight: bold;
  margin-bottom: 10rpx;
}
.list {
  display: flex;
}
.card {
  width: 45%;
  margin-right: 5%;
}
.card-image {
  width: 100%;
  height: 150rpx;
}
.card-name {
  font-size: 28rpx;
}
.card-desc {
  font-size: 24rpx;
  color: #666;
}
.all-btn {
  margin: 20rpx;
}
</style>
