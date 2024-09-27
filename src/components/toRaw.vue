<script setup>
import { reactive, toRaw } from "vue";

const counter = reactive({
  count: 0,
});

const incrementReactive = () => {
  counter.count++;
};

const incrementNonReactive = () => {
  const rawCounter = toRaw(counter);
  rawCounter.count++;
};
</script>

<template>
  <div>
    <h1>toRaw: {{ counter.count }}</h1>
    <button @click="incrementReactive">Увеличить реактивно</button>
    <button @click="incrementNonReactive">Увеличить без реактивности</button>
  </div>
</template>
