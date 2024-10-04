<script setup>
import { defineEmits, defineProps } from "vue";
import shortCircuit from "./shortCircuit.vue";

const { titleBtn, counter, titleComponent, list } = defineProps([
  "titleBtn",
  "counter",
  "titleComponent",
  "list",
]);

const emit = defineEmits([
  "incrementReactive",
  "disableReactivity",
  "closure",
  "incrementNonReactiveClone",
  "addNumberReactive",
  "addNumberNonReactive",
]);

const incrementReactive = () => {
  emit("incrementReactive");
};

const disableReactivity = () => {
  emit("disableReactivity");
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
    <h1>{{ titleComponent.markRaw }}: {{ counter.count }}</h1>
    <button @click="incrementReactive">{{ titleBtn.reactive }}</button>
    <button @click="disableReactivity">{{ titleBtn.nonReactive }}</button>
  </div>
  <shortCircuit
    :counter="counter"
    :titleBtn="titleBtn"
    :titleComponent="titleComponent"
    :list="list"
    @incrementReactive="incrementReactive"
    @closure="closure"
    @incrementNonReactiveClone="incrementNonReactiveClone"
    @addNumberReactive="addNumberReactive"
    @addNumberNonReactive="addNumberNonReactive"
  />
</template>
