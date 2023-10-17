<script setup lang="ts">
import { reactive } from "vue";
const state = reactive({
  firstNum: random(),
  secondNum: random(),
});
function generateQuestion() {
    state.firstNum = random();
    state.secondNum = random();
}
function random() {
  return Math.floor(Math.random() * 10);
}
</script>
<template>
  {{ state.firstNum }} + {{ state.secondNum }} =
  <button @click="generateQuestion">點一下</button>
</template>