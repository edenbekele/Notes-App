<template>
  <div class="note-selector" v-bind:class="{active: note === selectedNoteId }" >
      <p class="note-selector-title">{{ note.body | formatTitle }}</p>
      <p class="note-selector-timestamp">{{ note.timestamp | formatTimestamp }}</p>
  </div>
</template>

<script>
export default {
  name: "note-selector",
  props: ["note", "selectedNote"],
  filters: {
    formatTitle: function(body) {
      var maxLength = 20;
      if (body.length > maxLength) {
        return body.substring(0, maxLength - 3) + "...";
      } else if (body.length === 0) {
        return "New note";
      } else {
        return body;
      }
    },
    formatTimestamp: function(timestamp) {
      return new Date(timestamp).toUTCString();
    },
  },
};
</script>