<template>
  <div v-show="showModal" class="overlay">
    <Modal @addNote="addNote" />
  </div>
  <ExpandedNote />
  <main>
    <Header />
    <Note />
  </main>
</template>

<script setup>
import { provide, ref } from "vue";
import { useToast } from "vue-toastification";
import Header from "./components/Header.vue";
import Modal from "./components/Modal.vue";
import Note from "./components/Note.vue";
import ExpandedNote from "./components/ExpandedNote.vue";

const showModal = ref(false);
const expandNote = ref(false);
const notes = ref([]);
const newTitle = ref("");
const newDesc = ref("");
const toast = useToast();

const addNote = () => {
  if (newTitle.value.length > 0 && newDesc.value.length > 0) {
    notes.value.push({
      id: Math.floor(Math.random() * 1000000),
      title: newTitle.value,
      desc: newDesc.value,
      expandNote: expandNote.value,
    });
    showModal.value = false;
    newTitle.value = "";
    newDesc.value = "";
    toast.success("Note has been successfully created! Please tap to open it.");
  } else {
    return toast.error("Both fields must not be empty!");
  }
};

provide("showModal", showModal);
provide("newTitle", newTitle);
provide("newDesc", newDesc);
provide("notes", notes);
</script>
