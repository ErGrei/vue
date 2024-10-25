<script setup>
import { ref } from "vue";

let counter = ref({
  count: 0,
});

const titleComponent = {
  markRaw: "markRaw",
};

const incrementReactive = () => {
  counter.value.count++;
};

defineExpose({
  counter,
  incrementReactive,
})
</script>

<template>
  <div>
    <h1>{{ titleComponent.markRaw }}: {{ counter.count }}</h1>
    <button @click="incrementReactive">Увеличить счетчик</button>
  </div>
</template>
