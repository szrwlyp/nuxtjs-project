<template>
  <div>
    <!-- 头部组件 -->
    <AppHeader />

    <!-- 轮播图 -->
    <carouselComp :source-data="caroselData"></carouselComp>

    <!-- 主体内容 -->
    <div class="main">
      <nuxt />
    </div>

    <!-- 底部组件 -->
    <AppFooter></AppFooter>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const caroselData = ref([
  {
    url: 'https://www-file.huawei.com/-/media/corp2020/home/banner/8/hecs-light-pc.jpg',
    // caption: 'First slide',
    // text: 'Nulla vitae elit libero, a pharetra augue mollis interdum.',
  },
  {
    url: 'https://www-file.huawei.com/-/media/corp2020/home/banner/8/vmall-818-v2.jpg',
    // caption: 'First slide',
    // text: 'Nulla vitae elit libero, a pharetra augue mollis interdum.',
  },

  // {
  //   url: 'https://www.chaochuang.com.cn/style/images/banner-1.jpg',
  //   // caption: 'First slide',
  //   // text: 'Nulla vitae elit libero, a pharetra augue mollis interdum.',
  // },
  // {
  //   url: 'https://www.chaochuang.com.cn/style/images/banner-2.jpg',
  //   // caption: 'First slide',
  //   // text: 'Nulla vitae elit libero, a pharetra augue mollis interdum.',
  // },
  // {
  //   url: 'https://www.chaochuang.com.cn/style/images/banner-3.jpg',
  //   // caption: 'First slide',
  //   // text: 'Nulla vitae elit libero, a pharetra augue mollis interdum.',
  // },
])
</script>
<style scoped>
.main {
  /* width: 1200px; */
  margin: 0 auto;
}
</style>
