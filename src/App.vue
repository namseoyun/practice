<template>
  <h1>영화정보</h1>
  <div v-for="(movie, i) in data" :key="i" class="item">
    <figure>
      <img :src="`${movie.imgUrl}`" :alt="movie.title">
    </figure>
    <div class="info">
      <h3 class="bg-yellow">{{ movie.title }}</h3>
      <p>개봉: {{ movie.year }}</p>
      <p>장르: {{ movie.category }}</p>
      <button @click="increseLike(i)">좋아요</button> <span>{{ movie.like }}</span>
    </div>
  </div>
</template>

<script>
  import data from './assets/movies';
  
  export default {
    name: 'App',
    data() {
      return {
        data: data
      }
    },
    methods: { // 함수
      increseLike(i) {
        this.data[i].like += 1;
      }
    }
  }
</script>

<style>
.bg-yellow {
  background: yellow;
}
</style>
