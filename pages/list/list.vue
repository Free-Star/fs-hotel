<template>
  <view class="page">
    <view class="list">
      <view class="card" v-for="(room, index) in rooms" :key="index" @click="toDetail(room)">
        <image :src="room.img" class="card-image" />
        <view class="card-name">{{ room.name }}</view>
        <view class="card-desc">{{ room.desc }}</view>
      </view>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      rooms: [
        { img: '/static/img/r1.jpg', name: '房源A', desc: '舒适大床房' },
        { img: '/static/img/r2.jpg', name: '房源B', desc: '海景套房' },
        { img: '/static/img/r3.jpg', name: '房源C', desc: '温馨单间' }
      ]
    }
  },
  methods: {
    toDetail(room) {
      uni.navigateTo({ url: '/pages/detail/detail?name=' + room.name })
    }
  }
}
</script>

<style>
.list {
  display: flex;
  flex-wrap: wrap;
  padding: 20rpx;
}
.card {
  width: 48%;
  margin: 1%;
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
</style>
