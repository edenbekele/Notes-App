<template>
  <div class="note-selectors">
    <NoteSelector 
      v-for="note in transformedNotes" 
      v-bind:note="note" 
      v-bind:selectedNote="selectedNote"
      v-bind:key="note.id" 
      v-on:click.native="selectNote(note)"
      />
  </div>
</template>

<script>
import NoteSelector from "./NoteSelector";

export default {
  name: "note-selectors",
  props: ["notes", "transformedNotes", "selectedNote"],
  methods: {
    selectNote: function(note) {
      this.$emit("selectNote", note);
    },
  },
  components: {
    NoteSelector,
  },
};
</script>