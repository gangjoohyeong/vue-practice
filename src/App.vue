<template>
  <Transition name="fade">
    <DetailPage :onerooms="onerooms" :isClick="isClick" @closeModal="modalIsOpen = false" :modalIsOpen="modalIsOpen" />
  </Transition>

  <div class="menu">
    <a v-for="menu in menus" :key="menu"> {{ menu }}</a>
  </div>

  <DiscountBanner v-if="showDiscountBanner == true" :saleRate="saleRate"/>
  <button @click="sortBack">기본 정렬</button>
  <button @click="priceSortAsc">낮은 가격순 </button>
  <button @click="priceSortDesc">높은 가격순</button>
  <button @click="nameSortAsc">이름순</button>
  <button @click="nameSortDesc">이름역순</button>
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
    saleRate : 30,
    showDiscountBanner : true,
    sortItem : 0,
    oneroomsOrigin : [...data],
    isClick : 0,
    onerooms : data,
    modalIsOpen : false,
    products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
    menus : ['Home', 'Shop', 'MyPage'],
  }
},
  methods : {
    increase() {
      this.nClick += 1;
    },
    priceSortAsc() {
      this.onerooms.sort(function(a, b) { return a.price-b.price } );
    },
    priceSortDesc() {
      this.onerooms.sort(function(a, b) { return b.price-a.price } );
    },
    nameSortAsc() {
      this.onerooms.sort(function(a, b) {
        if(b.title < a.title) return 1;
        if(b.title > a.title) return -1;
        if(b.title === a.title) return 0;
      });
    },
    nameSortDesc() {
      this.onerooms.sort(function(a, b) {
        if(a.title < b.title) return 1;
        if(a.title > b.title) return -1;
        if(b.title === b.title) return 0;
      });
    },
    sortBack() {
      this.onerooms = [...this.oneroomsOrigin];
    },
  },

  mounted() {
    // setTimeout(()=> {
    //   this.showDiscountBanner = false;
    // }, 2000);
    setInterval(() => {
      this.saleRate = this.saleRate - 1;
      if (this.saleRate == 0) {
        this.saleRate = 30;
      }
    }, 1000); 
    // 1초마다 실행하는 함수
  },

  components: {
    DiscountBanner : DiscountBanner,
    DetailPage : DetailPage,
    ProductCard : ProductCard,
  }
}
</script>

<style>

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

