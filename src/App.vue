<template>
  <div id="app">
    <h1 class="my-3">Dtoolz Word Translator</h1>
    <h4 class="mt-3">
      input any word, submit to translate to the chosen language in the
      dropdown.
    </h4>
    <wordInput v-on:formSubmit="wordTranslate"></wordInput>
    <wordOutput v-text="wordTranslated" ></wordOutput>
  </div>
</template>

<script>
import wordInput from "./components/wordInput";
import wordOutput from "./components/wordOutput";

export default {
  name: "App",
  components: {
    wordInput,
    wordOutput
  },
  data: function(){
    return {
      wordTranslated: ''
    }
  },
  methods: {
    wordTranslate: function(word) {
      // alert(word);
      this.$http.get(
        "https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20200316T144937Z.93dc9dc5d746e1b2.f26ab83c43b2584761480613c7590cddad2ac904&lang=fr&text=" +
          word
      ).then((response) => {
          //console.log(response);
         this.wordTranslated =  response.body.text[0];
      });
    }
  }
};
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
