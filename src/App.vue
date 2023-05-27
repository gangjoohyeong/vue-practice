<template>
  <img alt="Vue logo" src="./assets/logo.png">

  <div class="menu">
    <a v-for="menu in menus" :key="menu"> {{ menu }}</a>
  </div>

  <div v-for="(product, idx) in products" :key="idx">
    <h4> {{ product }}</h4>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
  return {
    products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
    prices : [24000, 37000, 13000],
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
