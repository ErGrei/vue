<script setup>
import { reactive } from "vue";

class Counter {
  constructor() {
    this.count = 0;
  }
  increment() {
    this.count++;
  }
}
const counter = reactive(new Counter());

const addNumberReactive = () => {
  counter.count++;
};
const addNumberNonReactive = () => {
  counter.increment();
};



</script>

<template>
  <div>
    <h1>classCount: {{ counter.count }}</h1>

    <button @click="addNumberReactive">Добавить число реактивно</button>

    <button @click="addNumberNonReactive">
      Добавить число без реактивности
    </button>
  </div>
</template>