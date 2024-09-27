<script setup>
import { reactive } from "vue";

const state = reactive({
  count: 0,
});

let nonReactiveCount = state.count;

const incrementReactive = () => {
  state.count++;
};

const closure = () => {
  console.log("Состояние count внутри замыкания:", nonReactiveCount);
  nonReactiveCount += 1;
};
</script>

<template>
  <div>
    <h1>shortCircuit: {{ state.count }}</h1>
    <button @click="incrementReactive">Увеличить реактивно</button>
    <button @click="closure">Увеличивается без реактивности</button>
  </div>
</template>
