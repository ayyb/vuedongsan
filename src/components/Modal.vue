<template>
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
      <img :src="dataList[detailNumber].image" style="width:500px">
      <span @click="closeModal">닫기</span>
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
    data(){
        return{
            // modal :false,
        }
    },
    methods: {
        // closeModal(){
        //   this.modal = false;
        // }
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