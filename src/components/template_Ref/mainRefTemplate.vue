<script setup>
import { onMounted, ref, useTemplateRef } from "vue";
import toRawComp from "./list/toRawComp.vue";

// const toRawCompRef = useTemplateRef("toRawComp");

const toRawCompRef = ref(null)

const updateChildComponents = () => {
  toRawCompRef.value.incrementReactive();
  console.log(toRawCompRef.value);
};
</script>

<template>
  <button @click="updateChildComponents">
    Обновить данные в дочернем компоненте
  </button>
  <toRawComp ref="toRawCompRef" />
</template>
