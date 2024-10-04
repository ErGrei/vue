<script setup>
import { inject } from "vue";
import shortCircuit from "./shortCircuit.vue";

const counter = inject('counter');
const titleBtn = inject('titleBtn');
const titleComponent = inject('titleComponent');
const incrementReactive = inject('incrementReactive');
const disableReactivity = inject('disableReactivity');
</script>

<template>
  <div>
    <h1>{{ titleComponent.markRaw }}: {{ counter.count }}</h1>
    <button @click="incrementReactive">{{ titleBtn.reactive }}</button>
    <button @click="disableReactivity">{{ titleBtn.nonReactive }}</button>
  </div>
  <shortCircuit/>
</template>
