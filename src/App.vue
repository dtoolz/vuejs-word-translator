<template>
  <div class="container-fluid text-white text-center" id="app">
    <div class="gendiv">
      <h1 class="mb-3 pt-3 text-su">Dtoolz Word Translator</h1>
      <h3 class="mt-3 font-weight-normal text-capitalize lead">
        input words, click the translate button to translate to the chosen
        language in the selected option. <br />
        available languages includes french, spanish, chinese, german, italian,
        russian, portuguese.
      </h3>
      <div class="my-4 text-capitalize">
        <span class="underline">Translation is shown below :</span>
      </div>
      <wordOutput v-text="wordTranslated"></wordOutput>
      <div class="underline-a"></div>
      <wordInput v-on:formSubmit="wordTranslate"></wordInput>
    </div>
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
  data: function() {
    return {
      wordTranslated: ""
    };
  },
  methods: {
    wordTranslate: function(word, language) {
      // alert(word);
      this.$http
        .get(
          "https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20200316T144937Z.93dc9dc5d746e1b2.f26ab83c43b2584761480613c7590cddad2ac904&lang=" +
            language +
            "&text=" +
            word
        )
        .then(response => {
          //console.log(response);
          this.wordTranslated = response.body.text[0];
        });
    }
  }
};
</script>

<style>
#app {
  background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)),
    url("~@/assets/black.jpg") no-repeat center;
  background-size: cover;
  height: 100%;
}
.underline {
  border-bottom: 3px solid rgb(196, 235, 196);
  color: rgb(196, 235, 196);
  font-size: 20px;
}
.text-su{
  color: rgb(196, 235, 196);
}
.underline-a {
  border-bottom: 1px solid rgb(196, 235, 196);
  color: rgb(196, 235, 196);
  font-size: 20px;
}
.gendiv {
  margin-left: 200px;
}
@media (min-width: 768px) {
  .gendiv {
    margin-left: 200px;
  }
}
@media (min-width: 600px) {
  .gendiv {
    margin-left: 150px;
  }
}
@media (min-width: 500px) {
  .gendiv {
    margin-left: 100px;
  }
}
@media (min-width: 400px) {
  .gendiv {
    margin-left: 60px;
  }
}
@media (min-width: 300px) {
  .gendiv {
    margin-left: 30px;
  }
}
</style>
