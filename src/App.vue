<template>
  <DetailPage :onerooms="onerooms" :isClick="isClick" :modalIsOpen="modalIsOpen" />

  <div class="menu">
    <a v-for="menu in menus" :key="menu"> {{ menu }}</a>
  </div>

  <DiscountBanner/>


<ProductCard :oneroom="onerooms[i]" v-for="(a, i) in onerooms" :key="a"/>

<!-- <div v-for="(oneroom, i) in onerooms" :key="i"> -->
  <!-- <img :src="onerooms[i].image" class="room-img"> -->
  <!-- <h4 @click="modalIsOpen = true; isClick = i">{{  onerooms[i].title }}</h4> -->
  <!-- <p>{{ onerooms[i].price }}원</p> -->
<!-- </div> -->
</template>


<script>

import data from './assets/oneroom.js';
import DiscountBanner from './DiscountBanner.vue';
import DetailPage from './DetailPage.vue';
import ProductCard from './ProductCard.vue';

export default {
  name: 'App',
  data(){
  return {
    isClick : 0,
    onerooms : data,
    modalIsOpen : false,
    products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
    menus : ['Home', 'Shop', 'About'],
  }
},
  methods : {
    increase() {
      this.nClick += 1;
    },
  },
  components: {
    DiscountBanner : DiscountBanner,
    DetailPage : DetailPage,
    ProductCard : ProductCard,
  }
}
</script>

<style>

body {
  margin : 0
}
div {
  box-sizing : border-box;
}
.discount {
  background: #eee;
  padding: 10px;
  margin: 10px;
  border-radius: 5px;
}

.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}
.room-img {
  width: 100%;
  margin-top:40px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background : darkslateblue;
  padding : 15px;
  border-radius : 5px;
}
.menu a {
  color : white;
  padding : 10px;
}
</style>