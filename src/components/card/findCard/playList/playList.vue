<template>
  <div class="playlist-find" @click="jumpPlayListsDetail(data.id)">
    <img :src="data.coverImgUrl + '?param=500y500'">
    <!--当懒加载时div下图片源地址不会更新，故此处不适用懒加载-->
    <!--<img v-lazy="data.coverImgUrl + '?param=500y500'" lazy="loading">-->
    <h1 style="-webkit-box-orient: vertical;">{{data.name}}</h1>
    <p>by {{data.creator.nickname}}</p>
  </div>
</template>

<script>
  export default {
    name: 'v-play-list',
    props: {
      data: {
        type: Object
      }
    },
    methods: {
      jumpPlayListsDetail(id) {
        this.$router.push({
          path: '/playLists/' + id
        });
      }
    }
  };
</script>
<style lang="stylus" rel="stylesheet/stylus" scoped>
  @import 'playList.styl';
</style>
