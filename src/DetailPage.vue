<template>
<div class="black-bg" v-if="modalIsOpen == true">
    <div class="white-bg">
      <h4> {{ onerooms[isClick].title }} </h4>
      <img :src="onerooms[isClick].image" style="width:100%">
      <p> {{ onerooms[isClick].content }} </p>
      <p> {{ onerooms[isClick].price }}원 </p>
    <button @click="modalIsOpen = false">닫기</button>
    </div>    
  </div>
</template>

<script>
export default {

}
</script>

<style>

</style>