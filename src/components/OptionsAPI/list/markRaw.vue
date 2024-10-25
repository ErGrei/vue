<script>
export default {
  data() {
    return {
      counter: { count: 0 },
      titleComponent: {
        markRaw: "markRaw",
      },
    };
  },
  methods: {
    incrementReactive() {
      this.counter.count++;
    },
  },
};
</script>

<template>
  <div>
    <h1>{{ titleComponent.markRaw }}: {{ counter.count }}</h1>
    <button @click="incrementReactive">Увеличить счетчик</button>
  </div>
</template>
