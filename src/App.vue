<script setup>// 且因為 vite 的原因，所以不需要特別寫出 return
import { ref } from 'vue'; // 需要透過引用的方式，取出方法 from 'vue' 的字體大小寫要跟 main.js 的相同
const num = ref(2);
function clickMe() {
  num.value++;
};

</script>

<template>
  {{ num }}
  <button type="button" v-on:click="clickMe">點我</button>
</template>