<template>
   <div class="toolbar">
      <button 
      class="toolbar-button" 
      style="margin-right: .5em" 
      v-on:click="clickNew" 
      >New</button>
      <button class="toolbar-button" v-on:click="clickDelete">Delete</button>
      <input 
        type="text" 
        class="toolbar-search" 
        placeholder="Search..." 
        v-bind:value="searchNoteText" 
        v-on:input="inputSearchNoteText($event)">
    </div>
</template>

<script>
export default {
  name: "toolbar",
  props: ["searchNoteText"],
  methods: {
    clickNew: function() {
      this.$emit("clickNew");
    },
    clickDelete: function() {
      this.$emit("clickDelete");
    },
    inputSearchNoteText: function($event) {
      this.$emit("inputSearchNoteText", $event.target.value);
    },
  },
};
</script>

