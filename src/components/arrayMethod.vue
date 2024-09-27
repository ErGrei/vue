<script setup>
import { reactive } from "vue";

let list = reactive([1, 2, 3]);

const addNumberReactive = () => {
  const nextNumber = list[list.length - 1] + 1;
  list.push(nextNumber);
};

const addNumberNonReactive = () => {
  list = [0];
};
</script>

<template>
  <div>
    <h1>arrayMethod: {{ list }}</h1>

    <button @click="addNumberReactive">Добавить число реактивно</button>

    <button @click="addNumberNonReactive">
      Добавить число без реактивности
    </button>
  </div>
</template>
