<template>
  <div v-for="note in notes" :key="note.id">
    <div v-if="note.expandNote" class="expanded-overlay">
      <div class="expanded-container">
        <h2>{{ note.title }}</h2>
        <p>{{ note.desc }}</p>
        <button @click="note.expandNote = false">Close</button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { inject } from "vue";

const notes = inject("notes");
</script>
