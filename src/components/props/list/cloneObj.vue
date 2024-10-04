<script setup>
import { defineProps, defineEmits } from "vue";
import ArrayMethod from "./arrayMethod.vue";

const { titleBtn, counter, titleComponent, list } = defineProps([
  "titleBtn",
  "counter",
  "titleComponent",
  "list",
]);

const emit = defineEmits([
  "incrementReactive",
  "incrementNonReactiveClone",
  "addNumberReactive",
  "addNumberNonReactive",
]);

const incrementReactive = () => {
  emit("incrementReactive");
};

const incrementNonReactiveClone = () => {
  emit("incrementNonReactiveClone");
};

const addNumberReactive = () => {
  emit("addNumberReactive");
};
const addNumberNonReactive = () => {
  emit("addNumberNonReactive");
};
</script>

<template>
  <div>
    <h1>{{ titleComponent.cloneObj }}: {{ counter.count }}</h1>
    <button @click="incrementReactive">{{ titleBtn.reactive }}</button>
    <button @click="incrementNonReactiveClone">
      {{ titleBtn.nonReactive }}
    </button>
  </div>
  <ArrayMethod
    :titleBtn="titleBtn"
    :titleComponent="titleComponent"
    :list="list"
    @incrementReactive="incrementReactive"
    @addNumberReactive="addNumberReactive"
    @addNumberNonReactive="addNumberNonReactive"
  />
</template>
