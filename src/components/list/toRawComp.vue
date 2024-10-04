<script setup>
import { defineProps, defineEmits, ref, toRaw } from "vue";
import markRaw from "./markRaw.vue";

const { titleBtn, counter, titleComponent } = defineProps([
  "titleBtn",
  "counter",
  "titleComponent",
]);

const emit = defineEmits(["incrementReactive", "incrementNonReactive", "disableReactivity"]);

const incrementReactive = () => {
  emit("incrementReactive");
};
const incrementNonReactive = () => {
  emit("incrementNonReactive");
};

const disableReactivity = () => {
  emit("disableReactivity");
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
    @incrementReactive="incrementReactive"
    @disableReactivity="disableReactivity"
  />
</template>
