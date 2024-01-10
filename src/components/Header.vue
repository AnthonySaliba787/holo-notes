<template>
  <h1 class="main-title">Holo Notes</h1>
  <button class="add-note" @click="showModal = true">Create Note</button>
</template>

<script setup>
import { inject } from "vue";

const showModal = inject("showModal");
</script>
