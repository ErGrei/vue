<script setup>
import {  markRaw, defineProps} from 'vue';

// let state = reactive({
//   count: 0,
// });
// const incrementReactive = () => {
//   state.count++;
  
// };

const { titleBtn, counter, titleComponent } = defineProps([
  "titleBtn",
  "counter",
  "titleComponent",
]);


const emit = defineEmits(["incrementReactive", "disableReactivity"]);

const incrementReactive = () => {
  emit("incrementReactive");
};


const disableReactivity = () => {
  emit("disableReactivity");
};



</script>

<template>
  <div>
    <h1>{{ titleComponent.markRaw }}: {{ counter.count }}</h1>
    <button @click="incrementReactive">{{ titleBtn.reactive }}</button>
    <button @click="disableReactivity">{{ titleBtn.nonReactive }}</button>
  </div>
</template>