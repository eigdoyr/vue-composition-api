<template>
  <div class="modals">
    <h1>Modals</h1>
    <button @click="showModal = true">Show modal</button>
    <Modal
      v-if="showModal"
      @hideModal="showModal = false"
      title="My modal title (via prop)"
    >
      <!-- <template #title>My new title</template> -->
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Nisi
        voluptatibus accusamus repudiandae soluta, explicabo dolore aperiam.
        Enim nihil sequi consequuntur iusto, praesentium nam, sunt amet error
        quasi atque dolorum! Eos.
      </p>
    </Modal>
  </div>
</template>

<script setup>
/*
  imports
 */

import { ref } from "vue";
import Modal from "@/components/Modal.vue";

/*
  modals
 */

const showModal = ref(false);
</script>
