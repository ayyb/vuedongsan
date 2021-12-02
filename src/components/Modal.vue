<template>
  <!-- 상세페이지 내용 -->
  <div class="black-bg" v-if="modal == true">
    <div class="white-bg">
      <!-- 이미지 -->
      <img :src="dataList[detailNumber].image" style="width:500px">
      <!-- 상품명 -->
      <h4>{{dataList[detailNumber].title}}</h4>
      <!-- 상품설명 -->
      <p>{{dataList[detailNumber].content}}</p>
      <!-- 가격 -->
      <p>{{dataList[detailNumber].price}}</p>
      <!-- <input @input="month= $evnet.target.value"> -->
      <input v-model="month">
      <p>{{month}}개월 선택함 : {{dataList[detailNumber].price * month}} 원</p>
      <button @click="$emit('closeModal')">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
    name : 'Modal',
    props:{
        dataList : Array, //포맷은 { 데이터이름 : 자료형 형태로}
        modal : Boolean,
        detailNumber : Number,
    },
    watch:{
        month(data){
           if(isNaN(data) == true){
               alert('문자열 입력하지마세요.');
               this.month = 1;
           }
        }
    },
    data(){
        return{
            month: 0 
            // modal :false,
        }
    },
    beforeUpdate(){
    if(this.month == 2) {
      alert('2개월은 너무 적습니다.')
      this.month = 3;
    }
  },
    methods: {
    },
    
}
</script>

<style>
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