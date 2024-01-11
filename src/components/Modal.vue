<template>
  <div class="modal">
    <h2>Create Note</h2>
    <textarea
      v-model.trim="newTitle"
      name="title"
      id="title"
      placeholder="Title..."
      class="title-area"
    ></textarea>
    <textarea
      v-model.trim="newDesc"
      name="note"
      id="note"
      placeholder="Description..."
      class="desc-area"
    ></textarea>
    <button @click="triggerAddNote">Create</button>
    <button class="close" @click="showModal = false">Close</button>
  </div>
</template>

<script setup>
import { inject, defineEmits } from "vue";

const showModal = inject("showModal");
const newTitle = inject("newTitle");
const newDesc = inject("newDesc");
const emit = defineEmits(["addNote"]);

function triggerAddNote() {
  emit("addNote");
}
</script>
