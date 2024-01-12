<template>
  <div v-for="note in notes" :key="note.id">
    <div v-if="note.expandNote" class="expanded-overlay">
      <div class="expanded-container">
        <div class="text-container">
          <h2>{{ note.title }}</h2>
          <p>{{ note.desc }}</p>
        </div>
        <div class="button-container">
          <button class="deleteBtn" @click="deleteNote(note.id)">Delete</button>
          <button @click="note.expandNote = false">Close</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { inject, defineEmits } from "vue";

const notes = inject("notes");
const emit = defineEmits(["deleteNote"]);

function deleteNote(noteID) {
  emit("deleteNote", noteID);
}
</script>
