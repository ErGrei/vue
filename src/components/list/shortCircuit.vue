<script setup>
import { reactive, ref } from "vue";

const state = ref({
  count: 0,
});

const incrementReactive = () => {
  state.value.count++;
};

const closure = () => {
  let nonReactiveCount = state.value.count;
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
