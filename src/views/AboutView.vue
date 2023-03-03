<template>
  <div class="about">
    <h1>This is an about page</h1>
    <textarea v-autofocus />
  </div>
</template>

<script setup>
import { vAutofocus } from "@/directives/vAutoFocus";
</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
