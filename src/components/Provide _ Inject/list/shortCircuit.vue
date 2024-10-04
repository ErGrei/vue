<script setup>
import { inject } from "vue";
import cloneObj from "./cloneObj.vue";

const counter = inject('counter');
const titleBtn = inject('titleBtn');
const titleComponent = inject('titleComponent');
const list = inject('list');
const incrementReactive = inject('incrementReactive');
const closure = inject('closure');
</script>

<template>
  <div>
    <h1>{{ titleComponent.shortCircuit }}: {{ counter.count }}</h1>
    <button @click="incrementReactive">{{ titleBtn.reactive }}</button>
    <button @click="closure">{{ titleBtn.nonReactive }}</button>
  </div>
  <cloneObj  />
</template>
