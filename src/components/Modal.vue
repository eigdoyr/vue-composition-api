<template>
  <teleport to=".modals-container">
    <div class="modal">
      <h1>{{ title }}</h1>
      <slot />
      <button @click="handleButtonClick">Hide modal</button>
    </div>
  </teleport>
</template>

<script setup>
/*
props
 */

const props = defineProps({
  title: {
    type: String,
    default: "No title specified",
  },
});

/*
emits
 */

const emit = defineEmits(["hideModal"]);

/*
handle button click
 */

const handleButtonClick = () => {
  emit("hideModal");
};
</script>

<style>
.modal {
  background: beige;
  color: black;
  padding: 0.625rem;
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
}
</style>
