<script setup lang="ts">
import English from "./components/EnglishDB.vue";
import Chinese from "./components/ChineseDB.vue";  
import Math from "./components/MathDB.vue";  
import { reactive } from "vue";
let choice = reactive({title:'英文', value:"English"});
let items=[
  {title:'英文', value:"English"},
  {title:'中文', value:"Chinese"},
  {title:'數學', value:"Math"}]
</script>

<template>
  <div>
    <v-select label="請選擇" v-model="choice.value" :items="items" item-title="title" item-value="value">
    </v-select>
    <Suspense>
      <English v-if="choice.value === 'English'" />
      <Chinese v-else-if="choice.value === 'Chinese'" />
      <Math v-else-if="choice.value==='Math'" />
    </Suspense>
  </div>
</template>