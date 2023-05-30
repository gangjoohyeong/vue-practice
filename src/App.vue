<template>
  <div class="black-bg" v-if="modalIsOpen == true">
    <div class="white-bg">
      <h4> {{ onerooms[isClick].title }} </h4>
      <img :src="onerooms[isClick].image" class="room-img">
      <p> {{ onerooms[isClick].content }} </p>
      <p> {{ onerooms[isClick].price }}원 </p>
    <button @click="modalIsOpen = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="menu in menus" :key="menu"> {{ menu }}</a>
  </div>

<div v-for="(oneroom, i) in onerooms" :key="i">
  <img :src="onerooms[i].image" class="room-img">
  <h4 @click="modalIsOpen = true; isClick = i">{{  onerooms[i].title }}</h4>
  <p>{{ onerooms[i].price }}원</p>
</div>
</template>


<script>

import data from './assets/oneroom.js';

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
  increase1() {
    this.nClicks[0] += 1;
  },
  increase2() {
    this.nClicks[1] += 1;
  },
  increase3() {
    this.nClicks[2] += 1;
  }
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