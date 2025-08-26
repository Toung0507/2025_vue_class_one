<script setup>
import { ref } from 'vue';
// two_v-text_v-html
const num2 = ref(4);
const htmlTemplate = `<h1>這是一個 HTML 片段</h1>`;
</script>

<template>
  <div class="two_v-text_v-html">
    <h3>開始認識模板語言(也稱為指令)：{{ num2 }}</h3> <!-- 通常還是會用這個方式，自由度比較高 -->
    <h3 v-text="num2"></h3> <!-- v-text是一個顯示文字到畫面上的模板語言的方式 -->
    <p v-text="htmlTemplate"></p> <!-- 雖然 ref 的值是一個 html 標籤的寫法，但如果用 v-text 他不會解析 -->
    <p v-html="htmlTemplate"></p> <!-- 得用 v-html 才能夠去做正確的解析 -->
  </div>
</template>