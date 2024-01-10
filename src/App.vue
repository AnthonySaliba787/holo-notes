<template>
  <div v-show="showModal" class="overlay">
    <Modal />
  </div>
  <main>
    <Header />
    <Note />
  </main>
</template>

<script setup>
import { provide, ref } from "vue";
import Header from "./components/Header.vue";
import Modal from "./components/Modal.vue";
import Note from "./components/Note.vue";

const showModal = ref(false);

provide("showModal", showModal);
</script>
