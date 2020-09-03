<template>
  <div class="note-selector" v-bind:class="{active: selectedNoteId === note.id}" v-on:click="selectNote(note)">
      <p class="note-selector-title">{{ note.body | formatTitle }}</p>
      <p class="note-selector-timestamp">{{ note.timestamp | formatTimestamp }}</p>
  </div>
</template>

<script>
export default {
  name: "note-selector",
  filters: {
    formatTitle: function(body) {
      var maxLength = 20;
      if (body.length > maxLength) {
        return body.substring(0, maxLength - 3) + "...";
      } else {
        return body;
      }
    },
    formatTimestamp: function(timestamp) {
      return new Date(timestamp).toUTCString();
    },
  },
  props: ["note", "selectedNoteId"],
  methods: {
    selectNote: function(note) {
      console.log("This is the selected note", note, note.id);
      this.$emit("selectNote", note);
    },
  },
};
</script>