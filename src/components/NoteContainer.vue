<template>
  <div class="note-container">
      <NoteSelectors
       v-bind:notes="notes"
       v-bind:selectedNote="selectedNote"
       v-on:selectNote="selectNote"
      />
      <NoteEditor 
      v-bind:selectedNote="selectedNote"
      />
  </div>
</template>

<script>
import NoteSelectors from "./NoteSelectors";
import NoteEditor from "./NoteEditor";

export default {
  name: "note-container",
  props: ["notes"],
  components: {
    NoteSelectors,
    NoteEditor,
  },
};
</script>