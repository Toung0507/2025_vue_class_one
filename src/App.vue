<script setup>
// 因為 vite 的原因，所以不需要特別寫出 return

import One_ref from './components/One_ref.vue';
import Two_vText_vHtml from './components/Two_v-text_v-html.vue';
import Three_vModel from './components/Three_v-model.vue';
import Four_vBind from './components/Four_v-bind.vue';
import Five_vOn from './components/Five_v-on.vue';
import Six_vFor_vIf from './components/Six_v-for_v-if.vue';


</script>

<template>
  <one_ref></one_ref>
  <Two_vText_vHtml></Two_vText_vHtml>
  <three_v-model></three_v-model>
  <four_v-bind></four_v-bind>
  <Five_vOn></Five_vOn>
  <six_v-for_v-if></six_v-for_v-if>
</template>
