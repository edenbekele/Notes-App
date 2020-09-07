<template>
  <div class="note-container">
      <NoteSelectors
       v-bind:notes="notes"
       v-bind:transformedNotes="transformedNotes"
       v-bind:selectedNote="selectedNote"
       v-on:selectNote="selectNote"
      />
      <NoteEditor 
      v-bind:selectedNote="selectedNote"
      v-on:inputNoteEditor="inputNoteEditor"
      />
  </div>
</template>

<script>
import NoteSelectors from "./NoteSelectors";
import NoteEditor from "./NoteEditor";

export default {
  name: "note-container",
  props: ["notes", "transformedNotes", "selectedNote"],
  methods: {
    selectNote: function(note) {
      this.$emit("selectNote", note);
    },
    inputNoteEditor: function(body) {
      this.$emit("inputNoteEditor", body);
    },
  },
  components: {
    NoteSelectors,
    NoteEditor,
  },
};
</script>