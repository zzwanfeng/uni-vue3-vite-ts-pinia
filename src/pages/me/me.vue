<script lang="ts" setup>
import { useInit } from '@/hooks/useInit';

onLoad(() => {
  const { pageName, pagePath, pageQuery } = useInit();
  console.log(pageName, pagePath, pageQuery, 'pageName,pagePath, pageQuery');
});
</script>

<template>
  <Tabbars :current="2"></Tabbars>

  profile
</template>

<style lang="scss" scoped></style>
