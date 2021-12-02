<template>
<div>
  <img :src="item.image">
    <h4 :style="bold">{{item.title}}</h4>
    <p>{{item.price}}원</p>
    <!-- <button @click="increase(i)">허위매물 신고</button>
    <span>신고수 : {{checkCount[i]}}</span> -->
    <button @click="$emit('openModal')">상세페이지 보기</button>
</div>
</template>

<script>
export default {
    name : "Card",
    props:{
        item:Array,
    },
}
</script>

<style>

</style>