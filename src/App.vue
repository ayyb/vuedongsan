<template>
<div>
  <div class="menu">
    <a v-for="(item,index) in menu" :key="index">
      {{item}}
    </a>
  </div>
  <div v-for="(item,i) in products" :key="i">
    <h4 :style="bold">{{item}}</h4>
    <p>{{price2}}만원</p>
    <button @click="increase(i)">허위매물 신고</button>
    <span>신고수 : {{checkCount[i]}}</span>
  </div>
</div>
</template>

<script>
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
    }
  },
  components: {
  },
  methods: {
    //증가함수
    increase(i){
      let number = i;
      this.checkCount[number] += 1
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
</style>
