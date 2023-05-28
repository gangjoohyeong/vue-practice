<template>
  <img alt="Vue logo" src="./assets/logo.png">

  <div class="menu">
    <a v-for="menu in menus" :key="menu"> {{ menu }}</a>
  </div>

  <div>
  <h4>{{products[0]}}</h4>
  <p>50만원</p>
  <button @click="increase1">허위매물 신고</button> <span>신고 수: {{ nClicks[0] }}</span>
</div>
<div>
  <h4>{{products[1]}}</h4>
  <p>50만원</p>
  <button @click="increase2">허위매물 신고</button> <span>신고 수: {{ nClicks[1] }}</span>
</div>
<div>
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
