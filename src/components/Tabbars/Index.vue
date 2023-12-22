<script>
export default {
  props: {
    current: {
      type: Number,
      default: 0
    }
  },
  data() {
    return {
      TabBarList: [
        {
          type: 0,
          icon: '/static/tabbar/tab-home.png',
          selectIcon: '/static/tabbar/tab-home-active.png',
          name: '首页',
          url: '/pages/home/home'
        },
        {
          type: 1,
          icon: '/static/tabbar/tab-example-active.png',
          url: '/pages/home/home',
          name: '棒槌'
        },
        {
          type: 0,
          icon: '/static/tabbar/tab-personal.png',
          selectIcon: '/static/tabbar/tab-personal-active.png',
          name: '消息',
          url: '/pages/me/me'
        }
      ]
    };
  },
  methods: {
    navigatorTo(e) {
      // uni.redirectTo({
      //   url: e
      // });
      uni.switchTab({
        url: e
      });
    }
  }
};
</script>

<template>
  <view class="TabBar">
    <view
      v-for="(item, index) in TabBarList"
      :key="index"
      class="tab"
      @tap="navigatorTo(item.url)"
    >
      <template v-if="item.type === 0">
        <image
          class="imgsize"
          :src="current === index ? item.selectIcon : item.icon"
          mode="widthFix"
        ></image>

        <view :class="current === index ? 'active' : 'text'">{{
          item.name
        }}</view>
      </template>

      <template v-if="item.type === 1">
        <image class="midimgsize" :src="item.icon" mode="widthFix"></image>

        <view class="midtext">{{ item.name }}</view>
      </template>
    </view>
  </view>
</template>

<style scoped>
.TabBar {
  position: fixed;
  bottom: 0;
  height: 120rpx;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 1);
  background-color: white;
  background-size: 750rpx 88rpx;
  width: 100%;
  display: flex;
  justify-content: space-around;
  align-items: center;
  z-index: 1;
}
.tab {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.imgsize {
  width: 42rpx;
  height: 42rpx;
}

.text {
  margin-top: 10rpx;
  font-size: 24rpx;
  font-family: PingFangSC-Regular, PingFang SC;
  font-weight: 400;
  color: #bfc4c8ff;
  line-height: 20rpx;
}

.midimgsize {
  width: 98rpx;
  height: 98rpx;
  transform: translateY(-44rpx);
}
.midtext {
  transform: translateY(-40rpx);
  font-size: 24rpx;
  font-family: PingFangSC-Regular, PingFang SC;
  font-weight: 400;
  color: #bfc4c8ff;
  line-height: 20rpx;
}

.active {
  margin-top: 10rpx;
  font-size: 20rpx;
  font-family: PingFangSC-Regular, PingFang SC;
  font-weight: 400;
  color: #609eff;
  line-height: 20rpx;
}
</style>
