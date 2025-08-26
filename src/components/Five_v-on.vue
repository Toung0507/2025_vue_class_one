<script setup>
import { ref } from 'vue'; // 引用 Vue 的 ref 方法，用來建立「響應式變數」

// 一般的點擊事件
const handleClick = () => {
  console.log('我被觸發了');
};

// 表單送出的事件（搭配 @submit.prevent）
const submitForm = () => {
  console.log('表單送出啦');
};

// 按下 Enter 時，把「目前輸入的文字」存到「最後送出的文字」
const handleEnter = () => {
  finalText.value = inputNowText.value; // 把輸入框的值存到 finalText
};

// 定義「響應式變數」
// inputNowText：輸入框正在輸入中的文字（會隨 v-model 即時更新）
// finalText：使用者按下 Enter 後，確定下來的文字（才會更新）
const inputNowText = ref('');
const finalText = ref('');
</script>

<template>
  <div class="five_v-on">
    <!-- form 表單，監聽 submit 事件，.prevent 可以避免整頁重整 -->
    <form action="" @submit.prevent="submitForm">
      <!-- 按鈕的 type 預設是 submit，建議明確標註 -->
      <button type="button" v-on:click="handleClick">我是原本的v-on</button>
      <button type="button" @click="handleClick">我是縮寫的@</button>
      <button type="submit">點我送出吧</button>
    </form>

    <h2>事件修飾符，click.後面的就是</h2>
    <!-- @click.prevent = 阻止預設事件（preventDefault），這裡會讓 a 連結不跳頁 -->
    <p>.prevent事件修飾符，放在 a 連結中，就是取消預設的動作，讓他不會整個重整，preventdefault</p>
    <a href="#" @click.prevent="handleClick">點我</a>

    <h2>按鍵修飾符</h2>
    <p>
      <!-- 即時顯示輸入中的文字（隨 v-model 變動） -->
      目前輸入的文字是 {{ inputNowText }}
      <br>
      <!-- 只有按下 Enter 後才會更新的文字 -->
      最後送出的文字是 {{ finalText }}
    </p>

    <!-- v-model 綁定輸入框的值到 inputNowText -->
    <!-- @keydown.enter 監聽 Enter 鍵，觸發 handleEnter，把值存到 finalText -->
    <input type="text" v-on:keydown.enter="handleEnter" v-model="inputNowText">
  </div>
</template>
