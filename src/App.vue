<template>
<div>
  <!--Discount배너-->
  <Discount></Discount>
  <Modal :dataList="dataList" :modal="modal" :detailNumber="detailNumber"></Modal>

  <div class="menu">
    <a v-for="(item,index) in menu" :key="index">
      {{item}}
    </a>
  </div>
  <Card v-for="(item,i) in dataList" :key="i" :item="item" @openModal="modalOpen(i)"></Card>
</div>
</template>

<script>
import fakeData from './components/oneroom'
import Discount from './components/Discount.vue'
import Modal from './components/Modal.vue'
import Card from './Card.vue'
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
      dataList : fakeData,
      detailNumber:'',
      modal :false,
    }
  },
  components: {
    Discount,
    Modal,
    Card
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
