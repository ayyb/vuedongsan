<template>
<div>
  <div class="menu">
    <a v-for="(item,index) in menu" :key="index">
      {{item}}
    </a>
  </div>
  <img alt="Vue logo" src="./assets/logo.png">
  <div>
    원룸샵
    <h4 class="red" :style="red">XX 원룸</h4>
    <p>{{price1}}만원</p>
  </div>
  <div>
    <h4>XX 원룸</h4>
    <p>{{price2}}만원</p>
  </div>
  <ul v-for="(item,index) in products" :key="index">
    <h4 :style="bold">{{item}}</h4>
    <p>{{price2}}만원</p>
  </ul>
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
      menu: ['Home','Shop','About']
    }
  },
  components: {
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
