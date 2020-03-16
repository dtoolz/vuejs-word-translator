<template>
  <div id="app">
    <h1>Dtoolz Word Translator</h1>
    <h4>input any word, submit to translate to the chosen language in the dropdown.</h4>
    <wordInput></wordInput>
  </div>
</template>

<script>
import wordInput from "./components/wordInput";

export default {
  name: 'App',
  components : {
    wordInput
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
