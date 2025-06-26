<template>
  <view class="page">
    <swiper autoplay circular class="banner">
      <swiper-item v-for="(item, index) in images" :key="index">
        <image :src="item" class="banner-image" />
      </swiper-item>
    </swiper>
    <view class="info">
      <view class="title">{{ name }}</view>
      <view class="desc">请联系咨询</view>
      <view class="icons">
        <text>Wi-Fi</text>
        <text>独卫</text>
        <text>空调</text>
      </view>
    </view>
    <button type="primary" @click="toContact">立即联系</button>
  </view>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      images: [
        '/static/img/d1.jpg',
        '/static/img/d2.jpg'
      ]
    }
  },
  onLoad(options) {
    this.name = options.name || '房源';
  },
  methods: {
    toContact() {
      uni.navigateTo({ url: '/pages/contact/contact' })
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
.info {
  padding: 20rpx;
}
.title {
  font-size: 32rpx;
  font-weight: bold;
  margin-bottom: 10rpx;
}
.icons text {
  margin-right: 10rpx;
  font-size: 24rpx;
  color: #666;
}
</style>
