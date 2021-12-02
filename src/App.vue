<template>
<div>
  <!-- 상세페이지 내용 -->
  <div class="black-bg" v-if="modal == true">
    <div class="white-bg">
      <!-- 상품명 -->
      <h4>{{dataList[detailNumber].title}}</h4>
      <!-- 상품설명 -->
      <p>{{dataList[detailNumber].content}}</p>
      <!-- 가격 -->
      <p>{{dataList[detailNumber].price}}</p>
      <!-- 이미지 -->
      <img :src="dataList[detailNumber].image">
      <span @click="closeModal">닫기</span>
    </div>
  </div>
  <div class="menu">
    <a v-for="(item,index) in menu" :key="index">
      {{item}}
    </a>
  </div>
  <div v-for="(item,i) in dataList" :key="i">
    <img :src="item.image">
    <h4 :style="bold">{{item.title}}</h4>
    <p>{{item.price}}</p>
    <button @click="increase(i)">허위매물 신고</button>
    <span>신고수 : {{checkCount[i]}}</span>
    <button @click="modalOpen(i)">상세페이지 보기</button>
  </div>
</div>
</template>

<script>
import fakeData from './components/oneroom'
export default {
  name: 'App',
  data(){
    return{
      price1 : 600,
      price2 : 700,
      products: ['역삼동원룸','천호동원룸','마포구원룸'],
      red: 'color:red',
      bold: 'bold',
      menu: ['Home','Shop','About'],
      checkCount: [0,0,0],
      modal :false,
      dataList : fakeData,
      detailNumber:'',
    }
  },
  components: {
  },
  methods: {
    //증가함수
    increase(i){
      let number = i;
      this.checkCount[number] += 1
    },
    modalOpen(i){
      this.detailNumber = i;
      this.modal = true;
    },
    closeModal(){
      this.modal = false;
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
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
body {
  margin : 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height:100%;
  background: rgba(0,0,0,0.5);
  position: fixed; 
  padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
} 
</style>
