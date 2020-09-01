<template>
  <div id="app">
    <Toolbar />
    <NoteContainer />
  </div>
</template>

<script>
import Toolbar from "./components/Toolbar";
import NoteContainer from "./components/NoteContainer";

export default {
  name: "app",
  components: {
    Toolbar,
    NoteContainer,
  },
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
  background-color: #75a6c4;
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
