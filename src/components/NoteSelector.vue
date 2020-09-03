<template>
  <div class="note-selector" v-bind:class="{active: selectedNoteId === note.id}" v-on:click="selectNote(note)">
      <p class="note-selector-title">{{ note.body }}</p>
      <p class="note-selector-timestamp">{{ note.timestamp }}</p>
  </div>
</template>

<script>
export default {
  name: "note-selector",
  props: ["note", "selectedNoteId"],
  methods: {
    selectNote: function(note) {
      console.log("This is the selected note", note, note.id);
      this.$emit("selectNote", note);
    },
  },
};
</script>