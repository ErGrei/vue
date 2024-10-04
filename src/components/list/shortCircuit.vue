<script setup>
import { defineProps, defineEmits } from "vue";
import cloneObj from "./cloneObj.vue";

const { titleBtn, counter, titleComponent, list } = defineProps([
  "titleBtn",
  "counter",
  "titleComponent",
  "list",
]);

const emit = defineEmits([
  "incrementReactive",
  "closure",
  "incrementNonReactiveClone",
  "addNumberReactive",
  "addNumberNonReactive",
]);

const incrementReactive = () => {
  emit("incrementReactive");
};

const closure = () => {
  emit("closure");
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
    <h1>{{ titleComponent.shortCircuit }}: {{ counter.count }}</h1>
    <button @click="incrementReactive">{{ titleBtn.reactive }}</button>
    <button @click="closure">{{ titleBtn.nonReactive }}</button>
  </div>
  <cloneObj
    :counter="counter"
    :titleBtn="titleBtn"
    :titleComponent="titleComponent"
    :list="list"
    @incrementReactive="incrementReactive"
    @incrementNonReactiveClone="incrementNonReactiveClone"
    @addNumberReactive="addNumberReactive"
    @addNumberNonReactive="addNumberNonReactive"
  />
</template>
