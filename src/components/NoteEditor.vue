<template>
     <div class="note-editor">
          <p class="note-editor-info">{{ selectedNote.timestamp | formatTimestamp }}</p>
          <textarea class="note-editor-input"
            v-bind:value="selectedNote.body"
          >
            First note... 

            Note text here...
          </textarea>
      </div>
</template>

<script>
export default {
  name: "note-editor",
  props: ["selectedNote"],
};
</script>