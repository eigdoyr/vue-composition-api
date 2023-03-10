<template>
  <div class="modals">
    <h1>Modals</h1>
    <button @click="showModal = true">Show modal</button>
    <teleport to=".modals-container">
      <div v-if="showModal" class="modal">
        <h1>This is a modal</h1>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Nisi
          voluptatibus accusamus repudiandae soluta, explicabo dolore aperiam.
          Enim nihil sequi consequuntur iusto, praesentium nam, sunt amet error
          quasi atque dolorum! Eos.
        </p>
        <button @click="showModal = false">Hide modal</button>
      </div>
    </teleport>
  </div>
</template>

<script setup>
/*
  imports
 */

import { ref } from "vue";

/*
  modals
 */

const showModal = ref(false);
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
