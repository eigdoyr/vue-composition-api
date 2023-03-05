<template>
  <div class="home">
    <h2 ref="appTitleRef">{{ appTitle }}</h2>
    <h3>{{ counterData.title }}</h3>
    <div>
      <button @click="decreaseCounter(2)" class="btn">--</button>
      <button @click="decreaseCounter(1)" class="btn">-</button>
      <span class="counter">{{ counterData.count }}</span>
      <button @click="increaseCounter(1)" class="btn">+</button>
      <button @click="increaseCounter(2)" class="btn">++</button>
    </div>

    <p>This counter is {{ oddOrEven }}</p>

    <div class="edit">
      <h4>Edit counter title:</h4>
      <input v-model="counterData.title" type="text" v-autofocus />
    </div>
  </div>
</template>

<script setup>
/*
imports
*/

import { ref, reactive, computed, watch } from "vue";
import { vAutofocus } from "@/directives/vAutoFocus";

/*
appTitle
*/

const appTitle = "My OK Counter App";

const appTitleRef = ref(null);

/*
counter
*/
const counterData = reactive({
  count: 0,
  title: "My Counter",
});

watch(
  () => counterData.count,
  (newCount) => {
    if (newCount === 20) {
      alert("Way to go! You made it to 20!! 🥳");
    }
  }
);

const oddOrEven = computed(() => {
  return counterData.count % 2 === 0 ? "even" : "odd";
});

const increaseCounter = (amount) => (counterData.count += amount);
const decreaseCounter = (amount) => (counterData.count -= amount);
</script>

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
