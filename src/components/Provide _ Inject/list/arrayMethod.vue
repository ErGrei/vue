<script setup>
import { inject } from "vue";

const titleBtn = inject("titleBtn");
const titleComponent = inject("titleComponent");
const list = inject("list");
const addNumberReactive = inject("addNumberReactive");
const addNumberNonReactive = inject("addNumberNonReactive");
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
