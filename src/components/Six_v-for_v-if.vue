<script setup>
import { ref } from 'vue'; // 需要透過引用的方式，取出方法 from 'vue' 的字體大小寫要跟 main.js 的相同

// v-for
const array = ref([
  {
    id: 1,
    name: '劉宇寧',
    age: 35
  },
  {
    id: 2,
    name: '經歷',
    age: 21
  },
  {
    id: 3,
    name: '未來',
    age: 55
  },
  {
    id: 4,
    name: '中獎的時間',
    age: 0.5
  }

]);

// v-if ,v-else ,v-show
const isvIfChecked = ref(false);
</script>

<template>

  <div class="Six_v-for">
    <!-- v-for="(兩個值:物件本身,索引) in 哪個陣列中" 然後還要設定 key 值 ，通常是要在陣列的物件中就有自己的值最好 -->
    <!-- v-for跟v-if很常搭配使用但不會寫在一起 -->
    <div v-for="(item, key) in array" v-bind:key="item.id">
      索引：{{ key }}
      <br>
      ＩＤ：{{ item.id }}
      <br>
      姓名：{{ item.name }}
      <br>
      資歷：{{ item.age }}
      <div v-if="item.age > 10">資歷大於 10 年</div>
      <div v-else>資歷少少的</div>
      <hr>
    </div>
    <hr>
    <input type="checkbox" v-model="isvIfChecked">{{ isvIfChecked }}
    <h3 v-if="isvIfChecked">v-if 下當 isvIfChecked == true 會顯示這行</h3>
    <h3 v-else>目前的 isvIfChecked 為 false</h3>
    <!-- v-show 跟 v-if 都是條件成立時，會出現，但是v-show的元素實際上還存在，只是被下了display:none，而v-if的則是整個元素被刪除 -->
    <h3 v-show="isvIfChecked">v-show下當 isvIfChecked == true 會顯示這行</h3>
  </div>

</template>