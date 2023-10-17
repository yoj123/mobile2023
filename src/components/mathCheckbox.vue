<script setup lang="ts">

import { reactive } from "vue";

let answer = "";
const state = reactive({ message: "", currentQuestion: 0,answer:[] });


let exams = [
      { question: "下列哪些為質數", answer: ["31", "71"], options: ["10", "31", "71", "26"] },
      { question: "何者為正數?", answer: ["22", "根號2"], options: ["22", "-3", "根號2", "0"] },
      { question: "哪那些為36的因數?", answer: ["2", "3"], options: ["7", "3", "11", "2"] },
      { question: "a+3b=0,a可能的質為3,6 ，請問b可能為何?", answer: ["-1", "-2"], options: ["33", "2", "-1", "-2","0"] },
      { question: "哪些屬於實數?", answer: ["正整數", "負數"], options: ["複數", "正整數", "負數", "根號(-22)"] }
    ];
    function generateQuestion() {
  if (exams[state.currentQuestion].answer.length === state.answer.length) {
    let correct = 0;
    for (var item of state.answer) {
      if (exams[state.currentQuestion].answer.includes(item)) {
        correct++;
      }
    }
    if (correct == exams[state.currentQuestion].answer.length) {
      state.message = "答案正確";
      if (state.currentQuestion + 1 < exams.length) {
        state.currentQuestion++;
        state.answer = []; //清空上次的答案，否則會讀到上次的值
      }
    } else {
      state.message = "答案錯誤";
    }
  } else {
    state.message = "答案錯誤";
  }
}
</script>
<template>
  <div>
    {{ exams[state.currentQuestion].question }}
    <span v-for="option in exams[state.currentQuestion].options">
    <input type="checkbox" v-model="state.answer" :value="option" />
    {{ option }}
  </span>
    {{ state.message }}
    <button @click="generateQuestion">下一題</button>
  </div>
</template>