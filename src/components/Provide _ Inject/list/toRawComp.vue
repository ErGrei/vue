<script setup>
import { inject } from "vue";
import markRaw from "./markRaw.vue";

const counter = inject("counter");
const titleBtn = inject("titleBtn");
const titleComponent = inject("titleComponent");
const incrementReactive = inject("incrementReactive");
const incrementNonReactive = inject("incrementNonReactive");
</script>

<template>
  <div>
    <h1>{{ titleComponent.toRaw }}: {{ counter.count }}</h1>
    <button @click="incrementReactive">{{ titleBtn.reactive }}</button>
    <button @click="incrementNonReactive">{{ titleBtn.nonReactive }}</button>
  </div>
  <markRaw />
</template>
