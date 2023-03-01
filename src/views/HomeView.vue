<template>
  <div class="home">
    <h3>{{ counterData.title }}</h3>
    <div>
      <button @click="decreaseCounter" class="btn">-</button>
      <span class="counter">{{ counterData.count }}</span>
      <button @click="increaseCounter" class="btn">+</button>
    </div>

    <div class="edit">
      <h4>Edit counter title:</h4>
      <input v-model="counterData.title" type="text" />
    </div>
  </div>
</template>

<script setup>
import { ref, reactive } from "vue";

// const counter = ref(0),
//   counterTitle = ref("My Counter :");

const counterData = reactive({
  count: 0,
  title: "My Counter",
});

const increaseCounter = () => counterData.count++;
const decreaseCounter = () => counterData.count--;
</script>

<!--
<script>
import { ref } from "vue";

export default {
  setup() {
    const counter = ref(0);

    const increaseCounter = () => counter.value++;
    const decreaseCounter = () => counter.value--;

    return {
      counter,
      increaseCounter,
      decreaseCounter,
    };
  },
};
</script>
-->

<style>
.home {
  text-align: center;
  padding: 1.25rem;
}

.btn,
.counter {
  font-size: 2.5rem;
  margin: 0.625rem;
}

.edit {
  margin-top: 3.75rem;
}
</style>
