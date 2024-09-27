<script setup>
import { reactive, ref, toRaw } from "vue";

const counter = ref({
  count: 0,
});

const incrementReactive = () => {
  counter.value.count++;
};

const incrementNonReactive = () => {
  const rawCounter = counter;
  rawCounter.value.count++;
};
</script>

<template>
  <div>
    <h1>toRaw: {{ counter.count }}</h1>
    <button @click="incrementReactive">Увеличить реактивно</button>
    <button @click="incrementNonReactive">Увеличить без реактивности</button>
  </div>
</template>
