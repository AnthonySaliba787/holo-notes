<template>
  <div class="notes-container">
    <div v-for="note in notes" :key="note.id" class="note-preview">
      <h2>{{ note.title }}</h2>
    </div>
  </div>
</template>

<script setup>
import { inject } from "vue";

const notes = inject("notes");
</script>
