<template>
  <view class="content">
    <slot />
  </view>
</template>

<script>
export default {
}
</script>

<style>
.content {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}
</style>
