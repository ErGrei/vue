<script setup>
import { ref, useTemplateRef } from "vue";
import markRaw from "./markRaw.vue";

const markRawRef = useTemplateRef("MarkRaw");

let counter = ref({
  count: 0,
});

const titleBtn = {
  reactive: "Увеличить реактивно",
  nonReactive: "Увеличить без реактивности",
};

const titleComponent = {
  toRaw: "toRaw",
  markRaw: "markRaw",
};

const incrementReactive = () => {
  counter.value.count++;
};

const updateMarkRawComponent = () => {
  markRawRef.value.incrementReactive();
};
defineExpose({
  counter,
  incrementReactive,
});
</script>

<template>
  <div>
    <h1>{{ titleComponent.toRaw }}: {{ counter.count }}</h1>
    <button @click="incrementReactive">{{ titleBtn.reactive }}</button>
    <button @click="updateMarkRawComponent">Обновить данные в MarkRaw</button>
  </div>
  <markRaw ref="MarkRaw" />
</template>
