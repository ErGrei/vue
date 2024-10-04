<script setup>
import { defineProps, defineEmits, ref, toRaw } from "vue";
import markRaw from "./markRaw.vue";

const { titleBtn, counter, titleComponent, list } = defineProps([
  "titleBtn",
  "counter",
  "titleComponent",
  "list",
]);

const emit = defineEmits([
  "incrementReactive",
  "incrementNonReactive",
  "disableReactivity",
  "closure",
  "incrementNonReactiveClone",
  "addNumberReactive",
  "addNumberNonReactive",
]);

const incrementReactive = () => {
  emit("incrementReactive");
};
const incrementNonReactive = () => {
  emit("incrementNonReactive");
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
    <h1>{{ titleComponent.toRaw }}: {{ counter.count }}</h1>
    <button @click="incrementReactive">{{ titleBtn.reactive }}</button>
    <button @click="incrementNonReactive">{{ titleBtn.nonReactive }}</button>
  </div>
  <markRaw
    :counter="counter"
    :titleBtn="titleBtn"
    :titleComponent="titleComponent"
    :list="list"
    @incrementReactive="incrementReactive"
    @disableReactivity="disableReactivity"
    @closure="closure"
    @incrementNonReactiveClone="incrementNonReactiveClone"
    @addNumberReactive="addNumberReactive"
    @addNumberNonReactive="addNumberNonReactive"
  />
</template>
