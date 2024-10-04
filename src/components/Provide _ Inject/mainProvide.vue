<script setup>
import { ref, toRaw, markRaw, provide } from "vue";
import toRawComp from "./list/toRawComp.vue"; 

let counter = ref({
  count: 0,
});

let list = ref([1, 2, 3]);

const titleBtn = {
  reactive: "Увеличить реактивно",
  nonReactive: "Увеличить без реактивности",
};

const titleComponent = {
  toRaw: "toRaw",
  markRaw: "markRaw",
  cloneObj: "cloneObj",
  shortCircuit: "shortCircuit",
  arrayMethod: "arrayMethod",
  classCount: "classCount",
};

const incrementReactive = () => {
  counter.value.count++;
};
const incrementNonReactive = () => {
  const rawCounter = toRaw(counter);
  rawCounter.value.count++;
  console.log(rawCounter);
};

const disableReactivity = () => {
  counter = markRaw({
    count: counter.value.count + 1,
  });

  console.log("Счётчик после отключения реактивности:", counter.count);
  counter = ref({
    count: 0,
  });
};
const closure = () => {
  let nonReactiveCount = counter.value.count;
  console.log("Состояние count внутри замыкания:", nonReactiveCount);
  nonReactiveCount += 1;
};

const incrementNonReactiveClone = () => {
  const clonedState = JSON.parse(JSON.stringify(counter.value));

  clonedState.count++;

  console.log("Состояние count в клоне", clonedState.count);
};

const addNumberReactive = () => {
  const nextNumber = list.value[list.value.length - 1] + 1;
  list.value.push(nextNumber);
};

const addNumberNonReactive = () => {
  list.value[3] = 0;
};


provide('counter', counter);
provide('titleBtn', titleBtn);
provide('titleComponent', titleComponent);
provide('list', list);
provide('incrementReactive', incrementReactive);
provide('incrementNonReactive', incrementNonReactive);
provide('disableReactivity', disableReactivity);
provide('closure', closure);
provide('incrementNonReactiveClone', incrementNonReactiveClone);
provide('addNumberReactive', addNumberReactive);
provide('addNumberNonReactive', addNumberNonReactive);
</script>

<template>
  <toRawComp /> 
</template>
