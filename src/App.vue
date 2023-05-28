<template>
  
  <div class="black-bg" v-if="modalIsOpen == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용임</p>
      <button @click="modalIsOpen = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="menu in menus" :key="menu"> {{ menu }}</a>
  </div>





  <div>
  <img src="./assets/room0.jpg" class="room-img">
  <h4 @click="modalIsOpen = true">{{products[0]}}</h4>
  <p>50만원</p>
  <button @click="increase1">허위매물 신고</button> <span>신고 수: {{ nClicks[0] }}</span>
</div>
<div>
  <img src="./assets/room1.jpg" class="room-img">
  <h4>{{products[1]}}</h4>
  <p>50만원</p>
  <button @click="increase2">허위매물 신고</button> <span>신고 수: {{ nClicks[1] }}</span>
</div>
<div>
  <img src="./assets/room2.jpg" class="room-img">
  <h4>{{products[2]}}</h4>
  <p>50만원</p>
  <button @click="increase3">허위매물 신고</button> <span>신고 수: {{ nClicks[2] }}</span>
</div>
</template>

<script>

export default {
  name: 'App',
  data(){
  return {
    modalIsOpen : false,
    nClicks: [0, 0, 0],
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
  margin-top: 10px;
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
