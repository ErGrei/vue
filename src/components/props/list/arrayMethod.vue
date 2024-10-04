<script setup>
import { defineProps, defineEmits, } from "vue";

const { titleBtn, counter, titleComponent, list } = defineProps([
  "titleBtn",
  "titleComponent",
  "list",
]);

const emit = defineEmits([
"addNumberReactive",
"addNumberNonReactive",
]);

const addNumberReactive = () => {
  emit("addNumberReactive");
};
const addNumberNonReactive = () => {
  emit("addNumberNonReactive");
};


// const addNumberReactive = () => {
//   const nextNumber = list[list.length - 1] + 1;
//   list.push(nextNumber);
// };

// const addNumberNonReactive = () => {
//   list[3] = [0];
// };
</script>

<template>
  <div>
    <h1>{{ titleComponent.arrayMethod }}: {{ list}}</h1>

    <button @click="addNumberReactive">{{ titleBtn.reactive }}</button>

    <button @click="addNumberNonReactive">
      {{ titleBtn.nonReactive }}
    </button>
  </div>
</template>
