  <script setup>
  import { reactive } from "vue";
  
  const state = reactive({
    count: 0
  });

  const incrementReactive = () => {
    state.count++;
  };
 
  const incrementNonReactive = () => {
    const clonedState = JSON.parse(JSON.stringify(state));

    clonedState.count++;

    console.log("Состояние count в клоне", clonedState.count);

    // Object.assign(state, clonedState);
  };
  </script>
  
  <template>
    <div>
      <h1>cloneObj: {{ state.count }}</h1>
      <button @click="incrementReactive">Увеличить реактивно</button>
      <button @click="incrementNonReactive">Увеличить без реактивности</button>
    </div>
  </template>