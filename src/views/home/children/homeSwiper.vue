<template>
  <swiper>
    <SwiperItem v-for="item in banners">
      <a :href="item.link">
        <img :src="item.image" alt="">
      </a>
    </SwiperItem>
  </swiper>
</template>


<script>
  import {Swiper, SwiperItem} from 'components/common/swiper'

  export default {
    name: "homeSwiper",
    components: {
      Swiper,
      SwiperItem
    },
    props: {
      "banners": Array
    },
  }

</script>

<style scoped>

</style>
