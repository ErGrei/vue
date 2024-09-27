<script setup>
import { reactive, markRaw } from 'vue';

let state = reactive({
  count: 0,
});
const incrementReactive = () => {
  state.count++;
  
};


const disableReactivity = () => {

  state = markRaw({
    count: state.count + 1, 
  });

  console.log('Счётчик после отключения реактивности:', state.count);
  state = reactive({
  count: 0,
});
};


</script>

<template>
  <div>
    <h1>Счётчик: {{ state.count }}</h1>
    <button @click="incrementReactive">Увеличить реактивно</button>
    <button @click="disableReactivity">Отключить реактивность</button>
  </div>
</template>