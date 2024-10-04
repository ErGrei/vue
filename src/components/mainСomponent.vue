<script setup>
import { reactive, ref, toRaw, markRaw } from "vue";
import toRawComp from "./list/toRawComp.vue";

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
</script>

<template>
  <toRawComp
    :counter="counter"
    :titleBtn="titleBtn"
    :titleComponent="titleComponent"
    @incrementReactive="incrementReactive"
    @incrementNonReactive="incrementNonReactive"
    @disableReactivity="disableReactivity"
  />
</template>
