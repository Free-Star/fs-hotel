<template>
  <view class="page">
    <view class="info">
      <view class="label">微信号：</view>
      <view class="value" @click="copyWx">{{ wechat }}</view>
    </view>
    <button @click="callPhone">拨打电话</button>
    <image src="/static/img/qrcode.jpg" class="qrcode" mode="widthFix" />
  </view>
</template>

<script>
export default {
  data() {
    return {
      wechat: 'hotel123',
      phone: '13800138000'
    }
  },
  methods: {
    copyWx() {
      uni.setClipboardData({ data: this.wechat })
    },
    callPhone() {
      uni.makePhoneCall({ phoneNumber: this.phone })
    }
  }
}
</script>

<style>
.page {
  padding: 20rpx;
}
.info {
  display: flex;
  margin-bottom: 20rpx;
}
.label {
  width: 150rpx;
}
.value {
  color: #007AFF;
}
.qrcode {
  width: 200rpx;
  margin-top: 20rpx;
}
</style>
