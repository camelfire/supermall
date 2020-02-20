<template>
  <!--  <recommend>-->
  <!--    <div class="recommend-item" v-for="item in recommends">-->
  <!--      <a :href="item.link">-->
  <!--        <img :src="item.image" alt="">-->
  <!--      </a>-->
  <!--    </div>-->
  <!--  </recommend>-->
  <div class="recommend">
    <div v-for="item in recommends" class="recommend-item">
      <a :href="item.link">
        <img :src="item.image" alt="">
        <div>{{item.title}}</div>
      </a>
    </div>
  </div>
</template>

<script>
  export default {
    name: `Recommend`,
    props: {
      "recommends": Array
    }
  }
</script>

<style scoped>
  .recommend {
    display: flex;
    width: 100%;
    text-align: center;
    font-size: 12px;

    padding: 10px 0 20px;
    border-bottom: 8px solid #eeeeee;
  }

  .recommend-item {
    flex: 1;
  }

  .recommend-item img {
    width: 65px;
    height: 65px;
    margin-bottom: 10px;
  }
</style>
