<template>
  <!-- <div class="start" :class="{ end : modalIsOpen }"> -->
  <Transition name="fade">
    <DetailPage :onerooms="onerooms" :isClick="isClick" @closeModal="modalIsOpen = false" :modalIsOpen="modalIsOpen" />
  </Transition>
  <!-- </div> -->

  <div class="menu">
    <a v-for="menu in menus" :key="menu"> {{ menu }}</a>
  </div>

  <DiscountBanner/>
  <ProductCard @openModal="modalIsOpen = true; isClick = $event" :oneroom="onerooms[i]" v-for="(a, i) in onerooms" :key="a"/>
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

/* .start {
  opacity: 0;
  transition: all 0.5s;
}

.end {
  opacity: 1;
} */

.fade-enter-from {
  opacity: 0;
}
.fade-enter-active {
  transition: all 0.5s;
}
.fade-enter-to {
  opacity: 1;
}
.fade-leave-from {
  opacity: 1;
}
.fade-leave-active {
  transition: all 0.5s;
}
.fade-leave-to {
  opacity: 0;
}



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
  background : #162f9b;
  padding : 15px;
  border-radius : 5px;
}
.menu a {
  color : white;
  padding : 10px;
}
</style>

