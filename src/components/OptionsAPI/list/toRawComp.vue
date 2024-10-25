<script>
import markRaw from "./markRaw.vue";

export default {
  components: {
    markRaw,
  },
  data() {
    return {
      counter: { count: 0 },
      titleBtn: {
        reactive: "Увеличить реактивно",
        nonReactive: "Увеличить без реактивности",
      },
      titleComponent: {
        toRaw: "toRaw",
        markRaw: "markRaw",
      },
      markRawRef: null,
    };
  },
  methods: {
    incrementReactive() {
      this.counter.count++;
    },
    updateMarkRawComponent() {
      this.markRawRef.incrementReactive();
    },
  },
  mounted() {
    this.markRawRef = this.$refs.markRawRef;
  },
};
</script>

<template>
  <div>
    <h1>{{ titleComponent.toRaw }}: {{ counter.count }}</h1>
    <button @click="incrementReactive">{{ titleBtn.reactive }}</button>
    <button @click="updateMarkRawComponent">Обновить данные в MarkRaw</button>
  </div>
  <markRaw ref="markRawRef" />
</template>
