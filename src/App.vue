<template>
  <div id="app">
    <div class="toolbar">
      <button class="toolbar-button" style="margin-right: .5em">New</button>
      <button class="toolbar-button">Delete</button>
      <input type="text" class="toolbar-search" placeholder="Search...">
    </div>
    <div class="note-container">
      <div class="note-selectors">
        <div class="note-selector active">
          <p class="note-selector-title">First note...</p>
          <p class="note-selector-timestamp">Timestamp here...</p>
        </div>
         <div class="note-selector">
          <p class="note-selector-title">Second note...</p>
          <p class="note-selector-timestamp">Timestamp here...</p>
        </div>
         <div class="note-selector">
          <p class="note-selector-title">Third note...</p>
          <p class="note-selector-timestamp">Timestamp here...</p>
        </div>
      </div>
      <div class="note-editor">
        <p class="note-editor-info">Timestamp here...</p>
        <textarea class="note-editor-input">
          First note... 

          Note text here...
        </textarea>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
};
</script>

<style>
/* RESET */
* {
  margin: 0;
  padding: 0;
  border: 0;
  outline: none;
  box-sizing: border-box;
}
/* LAYOUT */
#app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}
.toolbar {
  padding: 0.5em;
}
.toolbar-button,
.toolbar-search {
  padding: inherit;
  border-radius: 0.3em;
}
.toolbar-search {
  float: right;
}
.note-container {
  display: flex;
  flex: 1;
}
.note-selectors {
  flex: 0 0 13em;
}
.note-selector {
  padding: 1em;
}
.note-selector p {
  margin: 0;
}
.note-editor {
  display: flex;
  flex: 1;
  flex-direction: column;
}
.note-editor-info {
  padding: 0.5em;
  text-align: center;
}
.note-editor-input {
  display: flex;
  flex: 1;
  width: 100%;
  padding: 0 2em 0 2em;
}
/* COLORS */
* {
  color: #cccccc;
  background-color: #1b1b1b;
}
.toolbar {
  background-color: #205477;
}
.toolbar-button {
  background-color: #474343;
}
.toolbar-button:active {
  background-color: #7c5d5d;
}
.note-selectors {
  border-right: 1px solid #dcdadc;
}
.note-selector {
  border-bottom: 1px solid #dcdadc;
}
.note-selector.active {
  background-color: #bdae2d;
}
.note-selector-title {
  background-color: inherit;
}
.note-selector-timestamp {
  color: #626262;
  background-color: inherit;
}
.note-editor-info {
  color: #dcdadc;
}
/* TYPOGRAPHY */
body {
  font-family: "Tenor Sans", sans-serif;
}
.note-selector-title {
  font-weight: bold;
}
.note-selector-timestamp {
  font-size: 0.7em;
}
.note-editor,
.note-editor-input {
  font-family: "Tenor Sans", sans-serif;
  font-size: 0.9em;
}
</style>
