<script setup lang="ts">
import { onHide, onLaunch, onShow } from '@dcloudio/uni-app';
onLaunch(() => {
  console.log('App Launch');
  uni.hideTabBar();
});
onShow(() => {
  console.log('App Show');
  uni.hideTabBar();
});
onHide(() => {
  console.log('App Hide');
});
</script>

<style></style>
