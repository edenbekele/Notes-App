<template>
  <div class="note-selectors">
    <NoteSelector 
      v-for="note in transformedNotes" 
      v-bind:note="note" 
      v-bind:key="note.id" 
      />
  </div>
</template>

<script>
import NoteSelector from "./NoteSelector";

export default {
  name: "note-selectors",
  props: ["notes"],
  computed: {
    transformedNotes: function() {
      return this.notes.slice().sort(function(a, b) {
        return b.timestamp - a.timestamp;
      });
    },
  },
  components: {
    NoteSelector,
  },

  methods: {
    selectNote: function(note) {
      this.selectedNoteId = note.id;
    },
  },
};
</script>