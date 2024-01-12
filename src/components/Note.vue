<template>
  <div class="notes-container">
    <div
      v-for="note in notes"
      :key="note.id"
      class="note-preview"
      @click="note.expandNote = true"
    >
      <h3>{{ note.title }}</h3>
    </div>
  </div>
</template>

<script setup>
import { inject } from "vue";

const notes = inject("notes");
</script>
