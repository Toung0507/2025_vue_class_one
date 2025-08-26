<script setup>
import { ref } from 'vue';

// three_v-model
const text = ref('這是一段文字');
const city = ref('台北市');
const isChecked = ref(false);
const arrayCheckbox = ref([]);
const radioValue = ref('男');
</script>

<template>
  <div class="three_v-model">
    <!-- v-model 是雙向綁定，綁定後，就可以在修改時，同步去修改 ref 所設定的值，而不用自己去寫相關的回傳再設定 -->
    <!-- 最常用的就是適用在表單身上 -->
    <!-- 
      v-model 是「雙向綁定」：
      1. 當使用者在 input 輸入文字時 → 會自動更新對應的 ref 變數
      2. 當 ref 變數被程式修改時 → input 也會同步顯示新值
      ✅ 好處：不用自己寫 @input 事件 + 手動更新變數
    -->
    <h1> {{ text }}</h1>
    <input type="text" v-model="text">
    <br>
    <!-- 表單 - 不管是下拉式選單，單選多選，都一定要指定 value 才會正常運行 -->
    <!-- 下拉式選單 -->
    {{ city }}
    <select name="" id="" v-model="city">
      <option value="台北市">台北市</option>
      <option value="台中市">台中市</option>
      <option value="高雄市">高雄市</option>
      <option value="彰化市">4</option>
    </select>
    <br>
    <!-- checkbox 核取方塊 1. true false 2.array value -->
    {{ isChecked }}
    <input type="checkbox" name="" id="" v-model="isChecked"> <!-- 第一種方式純 true / false -->
    <br>
    <!-- 存放陣列的值 -->
    {{ arrayCheckbox }}
    <input type="checkbox" name="" id="" v-model="arrayCheckbox" value="劉宇寧">
    <input type="checkbox" name="" id="" v-model="arrayCheckbox" value="老大">
    <input type="checkbox" name="" id="" v-model="arrayCheckbox" value="寧哥">
    <br>
    <!-- radio 單一值 -->
    {{ radioValue }}
    <input type="radio" name="" id="" v-model="radioValue" value="男">
    <input type="radio" name="" id="" v-model="radioValue" value="女">
  </div>
</template>