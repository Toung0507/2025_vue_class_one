<script setup>
import { ref } from 'vue';

// four_v-bind
const imgUrl = ref('https://wx1.sinaimg.cn/mw2000/007Z6Djfgy1i4pyuio8i5j368b45m1l9.jpg');
const img2Url = ref('https://wx2.sinaimg.cn/mw2000/007Z6Djfly1i449ux3fuuj34tc37kb2e.jpg');
const isInputCheck = ref(false);
const isRotate = ref(false);
</script>

<template>
  <div class="four_v-bind">
    <hr>
    <!-- v-bind 更改 html 的屬性 -->
    <img v-bind:src="imgUrl" alt="">
    <img :src="img2Url" alt=""> <!-- v-bind 是全稱，但可以簡寫成 : 就好 -->
    <h3>可以套用在任何的屬性上</h3>
    <p>可不可以輸入呢？ {{ !isInputCheck }}
      <input type="checkbox" name="" id="" v-model="isInputCheck">
      <input type="text" :disabled="isInputCheck">
    </p>
    <h3>可以套用在行內樣式上</h3>
    <p>
      要不要旋轉一下呢？ {{ isRotate ? '好啊' : '不要' }}
      <input type="checkbox" name="" id="" v-model="isRotate">
    </p>
    <div class="box" v-bind:style="{ transform: isRotate ? 'rotate(45deg)' : null }">透過style新增css</div>
    <div class="box" v-bind:style="{ backgroundColor: isRotate ? 'red' : 'yellow' }">透過style新增css</div>
    <h3>也可以拿來控制是否要某個class</h3>
    <!-- 需要套用的 className:變數 -->
    <div class="box" :class="{ rotate: isRotate }">透過class控制css</div>

  </div>
</template>

<style>
img {
  max-width: 900px;
  min-height: 200px;
}

.box {
  height: 100px;
  width: 100px;
  background-color: red;
  transition: 0.5s all;
}

.rotate {
  transform: rotate(90deg);
}
</style>
