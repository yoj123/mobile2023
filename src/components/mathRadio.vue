<script setup lang="ts">
import { reactive } from "vue";
let answer = "";
const state = reactive({ message: "", currentQuestion: 0 });
let exams = [
  { question: "2的10次方", answer: "1024" },
  { question: "3的3次方", answer: "27" },
  { question: "11*11=", answer: "121" },
  { question: "2*2+5*3", answer: "19" },
  { question: "33/3+10", answer: "21" },

];
function generateQuestion() {
  if (exams[state.currentQuestion].answer === answer) {
    state.message = "答案正確";
    if (state.currentQuestion + 1 < exams.length) {
      state.currentQuestion++;
    }
  } else {
    state.message = "答案錯誤";
  }

}
</script>
<template>
  <div>
    {{ exams[state.currentQuestion].question }}
    <input type="text" v-model="answer" />
    {{ state.message }}
    <button @click="generateQuestion">下一題</button>
  </div>
</template>