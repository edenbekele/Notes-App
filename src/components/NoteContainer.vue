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
  props: ["note", "selectedNoteId"],
  methods: {
    selectNote: function(note) {
      console.log("This is the selected note", note, note.id);
      this.$emit("selectNote", note);
    },
  },
  components: {
    NoteSelectors,
    NoteEditor,
  },
};
</script>