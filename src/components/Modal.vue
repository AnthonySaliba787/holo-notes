<template>
  <div class="modal">
    <textarea
      name="title"
      id="title"
      placeholder="Title..."
      class="title-area"
    ></textarea>
    <textarea
      name="note"
      id="note"
      placeholder="Description..."
      class="desc-area"
    ></textarea>
    <p v-if="errorMsg">{{ errorMsg }}</p>
    <button>Create</button>
    <button class="close" @click="showModal = false">Close</button>
  </div>
</template>

<script setup>
import { inject, ref } from "vue";

const errorMsg = ref("");
const showModal = inject("showModal");
</script>
