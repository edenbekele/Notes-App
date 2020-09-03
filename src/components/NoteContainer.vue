<template>
  <div class="note-container">
      <NoteSelectors />
      <NoteEditor />
  </div>
</template>

<script>
import NoteSelectors from "./NoteSelectors";
import NoteEditor from "./NoteEditor";

export default {
  name: "note-container",
  components: {
    NoteSelectors,
    NoteEditor,
  },
};
</script>