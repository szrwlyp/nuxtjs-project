<template>
  <div>
    <b-carousel
      id="carousel-1"
      v-model="slide"
      :interval="4000"
      controls
      indicators
      background="#ababab"
      img-width="1024"
      img-height="400"
      style="text-shadow: 1px 1px 2px #333"
    >
      <b-carousel-slide
        v-for="(item, index) in sourceData"
        :key="index"
        :caption="item.caption"
        :text="item.text"
        :img-src="item.url"
      ></b-carousel-slide>

      <!-- <b-carousel-slide
        img-src="https://www.chaochuang.com.cn/style/images/banner-2.jpg"
      >
        <h1>Hello world!</h1>
      </b-carousel-slide> -->
    </b-carousel>
  </div>
</template>

<script setup lang="ts">
import { ref, toRefs } from 'vue'

interface IProps {
  sourceData: any
}
const props = defineProps<IProps>()

const { sourceData } = toRefs(props)
console.log(sourceData)

const slide = ref(0)

// const onSlideStart = (slide: number) => {
//   console.log(slide)
// }

// const onSlideEnd = (slide: number) => {
//   console.log(slide)
// }
</script>
