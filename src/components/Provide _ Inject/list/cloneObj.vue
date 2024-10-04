<script setup>
import { inject } from "vue";
import ArrayMethod from "./arrayMethod.vue";

const counter = inject("counter");
const titleBtn = inject("titleBtn");
const titleComponent = inject("titleComponent");
const incrementReactive = inject("incrementReactive");
const incrementNonReactiveClone = inject("incrementNonReactiveClone");

</script>

<template>
  <div>
    <h1>{{ titleComponent.cloneObj }}: {{ counter.count }}</h1>
    <button @click="incrementReactive">{{ titleBtn.reactive }}</button>
    <button @click="incrementNonReactiveClone">
      {{ titleBtn.nonReactive }}
    </button>
  </div>
  <ArrayMethod/>
</template>
