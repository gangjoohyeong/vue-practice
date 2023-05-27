<template>
  <img alt="Vue logo" src="./assets/logo.png">

  <div class="menu">
    <a v-for="menu in menus" :key="menu"> {{ menu }}</a>
  </div>

  <div>
  <h4>{{products[0]}}</h4>
  <p>50만원</p>
  <button @click="nClick += 1">허위매물 신고</button> <span>신고 수: {{ nClick }}</span>
</div>
<div>
  <h4>{{products[1]}}</h4>
  <p>50만원</p>
</div>
<div>
  <h4>{{products[2]}}</h4>
  <p>50만원</p>
</div>
</template>

<script>

export default {
  name: 'App',
  data(){
  return {
    nClick: 0,
    products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
    menus : ['Home', 'Shop', 'About'],
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
