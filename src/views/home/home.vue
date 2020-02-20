<template>
  <div id="home">
    <nav-bar class="home_nav">
<!--      <div slot= "center">购物街</div>-->
      <template v-slot:center>
        "购物街“
      </template>
    </nav-bar>
    <home-swiper :banners="banners"></home-swiper>
    <recommend :recommends="recommends"></recommend>
  </div>
</template>

<script>
  import NavBar from "components/common/navbar/NavBar";
  import HomeSwiper from './children/homeSwiper'
  import Recommend from "./children/recommend";


  import {getHomeMultidata} from "network/home";
  export default {
    name: 'home',
    components: {
      NavBar,
      HomeSwiper,
      Recommend

    },
    data() {
      return {
        result: null,
        banners: [],
        recommends: [],
      };
    },
    computed: {},
    watch: {},
    methods: {},
    created() {
      getHomeMultidata().then(res => {
        //箭头函数中的this指向上一级变量
        this.result = res;
        this.banners = res.data.banner.list;
        this.recommends = res.data.recommend.list;
        console.log(this.recommends);
      })
    }
  };
</script>

<style scoped>
  .home_nav {
    background-color: var(--color-tint);
  }
</style>
