<template>
<div class="black-bg" v-if="modalIsOpen == true">
    <div class="white-bg">
      <h4> {{ onerooms[isClick].title }} </h4>
      <img :src="onerooms[isClick].image" style="width:100%">
      <p> {{ onerooms[isClick].content }} </p>
      <!-- <input @input="month = $event.target.value"> -->
      <input v-model.number="month">
      <!-- <select v-model.number="month">
        <option>1개월</option>
        <option>3개월</option>
        <option>6개월</option>
        <option>12개월</option>
      </select> -->
      <p> {{ month }}개월: {{ (onerooms[isClick].price * month).toLocaleString() }}원 </p>
    <button @click="$emit('closeModal')">닫기</button>
    </div>    
  </div>
</template>

<script>
export default {
  name : 'DetailPage',
  data() {
    return {
      month : 1,
    }
  },
  watch : {
    month(x) {
      if (x > 12) {
        alert('12개월 이하만 가능합니다.');
        this.month = 12;
      }
      if (isNaN(x) == true) {
        alert('숫자만 입력 가능합니다.');
        this.month = 1;
      }
    },
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