<template>
  <div class="padd" id="wordInput">
      <h4 class="mt-3">Preview Your Input : {{ wordToTranslate }}</h4>
    <form class="container  mt-5" v-on:submit="formSubmit">
      <div class="form-div-a row">
        <div class="input-group mb-3">
          <div class="input-group-prepend">
            <span class="input-group-text" id="basic-addon1">Input</span>
          </div>
          <input
            type="text"
            class="form-control"
            placeholder="type words here..."
            aria-label="Username"
            aria-describedby="basic-addon1"
            v-model="wordToTranslate"
          />
        </div>
      </div>
      <div class="form-div-b row">
          <div class="input-group-prepend">
            <span class="input-group-text" id="basic-addon1">select language</span>
          </div>
        <select class="custom-select-md" v-model="language">
          <option value="fr">French</option>
          <option value="es">Spanish</option>
          <option value="zh">Chinese</option>
          <option value="de">German</option>
          <option value="it">Italian</option>
          <option value="ru">Russian</option>
          <option value="pt">Portuguese</option>
        </select>
        <input class="btn btn-success" type="submit" value="Translate" />
      </div>
    </form>
    
  </div>
</template>

<script>
export default {
  name: "wordInput",
  data() {
    return {
      wordToTranslate: "",
      language: ""
    };
  },
  created() {
    this.language = "fr";
  },
  methods: {
    formSubmit(e) {
      this.$emit("formSubmit", this.wordToTranslate, this.language); //sending typed input to app.vue component
      e.preventDefault();
    }
  }
};
</script>

<style scoped>
.padd {
    padding-bottom: 300px;
}
@media (min-width: 1200px) {
  .form-div-a{
  margin-left: 200px !important;
  margin-right: 300px !important;
  }
   .form-div-b{
  margin-left: 700px !important;
  margin-right: 50px !important;
  }
}

@media (min-width: 1000px) {
  .form-div-a{
  margin-left: 250px !important;
  margin-right: 200px !important;
  }
   .form-div-b{
  margin-left: 310px !important;
  margin-right: 150px !important;
  }
}

</style>
