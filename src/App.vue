<template>

  <div class="black-bg" v-if="modalOpen == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <button @click="modalOpen=false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="(a, i) in menus" :key="i">{{a}}</a>
  </div>

  <div v-for="a in products" :key="a">
    <h4>{{a}}</h4>
    <p>50 만원</p>
  </div>
  <!-- <div v-for="(a,i) in 3" :key="i">
    <h4 calss="red" :style="style1">{{products[i]}}</h4>
    <p>50 만원</p>
  </div> -->
  <div>
    <img :src="products[0].image" class="room-img">
    <h4 @click="modalOpen=true">{{products[0].title}}</h4>
    <p>{{products[0].price}}</p>
    <button @click="numbers[0]++">허위매물신고</button> <span>신고수 : {{numbers[0]}}</span>
    <button @mouseover="increasse">허위매물신고</button> <span>신고수 : {{numbers[0]}}</span>
  </div>
  <div>
    <img :src="products[1].image" class="room-img">
    <h4 calss="red" :style="style1">{{products[1].title}}</h4>
    <p>{{products[1].title}}</p>
    <button @click="numbers[1]++">허위매물신고</button> <span>신고수 : {{numbers[1]}}</span>
  </div>
  <div>
    <img :src="products[2].image" class="room-img">
    <h4 calss="red" :style="style1">{{products[2].title}}</h4>
    <p>{{products[2].title}}</p>
    <button @click="numbers[2]++">허위매물신고</button> <span>신고수 : {{numbers[2]}}</span>
  </div>
</template>

<script>

import datas from './assets/oneroom.js'

export default {
  name: 'App',
  data(){
    return{
      modalOpen: false,
      price1 : 80,
      price2 : 70,
      style1 : 'color : blue',
      menus : ["Home", "Products", "About"],
      products : datas,
      numbers : [0,0,0]
    }
  },
  methods : {
    increasse(number){
      return number++
    },
  },
  components: {
  }
}
</script>

<style>
body{
  margin:0
}
div {
  box-sizing: border-box;
}

.black-bg{
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}

.white-bg{
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a{
  color: white;
  padding: 10px;
}

.room-img{
  width: 100%;
  margin-top: 40px;
}



</style>
