<script>
import toRawComp from "./list/toRawComp.vue";

export default {
  components: {
    toRawComp,
  },
  data() {
    return {
      toRawCompRef: null,
    };
  },
  methods: {
    updateChildComponents() {
        this.toRawCompRef.incrementReactive();
    },
  },
  mounted() {
    this.toRawCompRef = this.$refs.toRawCompRef;
  },
};
</script>

<template>
  <button @click="updateChildComponents">
    Обновить данные в дочернем компоненте
  </button>
  <toRawComp ref="toRawCompRef" />
</template>
