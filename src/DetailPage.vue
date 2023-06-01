<template>
<div class="black-bg" v-if="modalIsOpen == true">
    <div class="white-bg">
      <h4> {{ onerooms[isClick].title }} </h4>
      <img :src="onerooms[isClick].image" style="width:100%">
      <p> {{ onerooms[isClick].content }} </p>
      <p> {{ onerooms[isClick].price }}원 </p>
    <button @click="$emit('closeModal')">닫기</button>
    </div>    
  </div>
</template>

<script>
export default {
  name : 'DetailPage',
  data() {

  },
  props : {
    onerooms : Array,
    isClick: Number,
    modalIsOpen: Boolean,
  }
}
</script>

<style>

</style>