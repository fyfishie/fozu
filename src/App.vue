<!--
 * @Author: fyfishie
 * @Date: 2023-04-07:21
 * @LastEditors: fyfishie
 * @LastEditTime: 2023-04-23:14
 * email: fyfishie@outlook.com
 * @Description: :)
-->
<script setup>
import {ref} from 'vue'
var count = ref(0)
function inc(){
  count.value++
}
function clk(){
  count.value++
  var gd = document.getElementById("gongde");
  gd.classList.remove("hid")
  gd.classList.add("dhc")
  setTimeout(recover,500)
}
function recover(){
  var gd = document.getElementById("gongde");
  gd.classList.remove("dhc")
  gd.classList.add("hid")

}
setInterval(inc,1000)
</script>

<template>
  <div class="container">
    <div class="hd">
      <div class="name">轻量级电子功德收集器</div>
      <div class="count">本机总功德：{{ count }}</div>
    </div>
    <div class="bum">
      <!-- <p>本机总功德</p> -->
      <!-- <div class="textcontainer">轻量级电子功德收集器</div> -->
      <div id="muyu" @click="clk"></div>
      <div class="hid vis" id="gongde">功德+1</div>
    </div>
  </div>
</template>

<style scoped>
.container{
  width: 100vw;
  height: 100vh;
  position: relative;
  text-align: center;
  /* display: flex; */
}
.hd{
  width: 100%;
  height: 30%;
  margin: auto;
  background-color: black ;
  text-align: center;
  display: flex;
  flex-direction: column;
}
.count{
  /* margin: auto; */
  margin-right: auto;
  margin-left: auto;
  margin-top: 10%;
  height: 40px;
  line-height: 40px;
  font-size: 30px;
  align-self: center;
  color:white;
  display: flex;
}
.name{
  margin: auto;
  height: 40px;
  line-height: 40px;
  font-size: 30px;
  align-self: center;
  color: white;
  display: inline;
}
.bum{
  width: 100%;
  height: 70%;
  background-color: black;
  margin: auto;
  display: flex;
  flex-direction: column;
  position: relative;
}
#muyu{
  display: inline;
  align-self: center;
  margin-top: 200px;
  width: 120px;
  height: 120px;
  font-size: 30px;
  /* background-color: #3498db; */
  /* border-radius: 5px; */
  /* border: #2980b9 solid 1px; */
  background-image: url("../public/images/muyu.jpg");
  background-repeat: no-repeat;
}
#muyu:hover{
  /* background-color: #227093; */
  cursor: pointer;
}
#muyu:active{
  background-color: #bff;
  transform: scale(0.9);
}
/* .inc:active + .txtc{ */
  /* visibility: visible; */
  /* transform: scale(1.1); */
  /* color: orange; */
  /* animation-name: dh;
  animation-duration: 2s; */
  /* } */
  #gongde{
    font-size: 25px;
    position: absolute;
    top: 120px;
    left: 55%;
  }
  .hid{
    visibility: hidden;
  }
  .dhc{
    transform: scale(1.1);
    color: white;
    animation-name: dh;
    animation-duration: 0.5s;
  }
@keyframes dh {
  from{
    color: white;
    top: 160px;
  }
  to{
    /* visibility: hidden; */
    color: white;
    top: 120px;
  }
}
</style>
