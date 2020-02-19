<template>
  <div id="home">
    <nav-bar class="home_nav">
      <div slot="center">购物街</div>
    </nav-bar>
  </div>
</template>

<script>
  import NavBar from "components/common/navbar/NavBar";
  import {getHomeMultidata} from "../../network/home";

  export default {
    name: 'home',
    components: {
      NavBar
    },
    data() {
      return {
        result: null
      };
    },
    computed: {},
    watch: {},
    methods: {},
    created() {
      getHomeMultidata().then(res => {
        //箭头函数中的this指向上一级变量
        this.result = res;
      })
    }
  };
</script>

<style scoped>
  .home_nav {
    background-color: var(--color-tint);
  }
</style>
