<template>
  <div id="wordInput">
    <form class="container mt-5" v-on:submit="formSubmit">
      <div class="col-md-9 input-group mb-3">
        <div class="input-group-prepend">
          <span class="input-group-text" id="basic-addon1">Word</span>
        </div>
        <input
          type="text"
          class="form-control"
          placeholder="input a word"
          aria-label="Username"
          aria-describedby="basic-addon1"
          v-model="wordToTranslate"
        />
        <input class="btn btn-success" type="submit" value="Translate">
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "wordInput",
  data(){
      return {
          wordToTranslate: ''
      }
  },
  methods : {
      formSubmit(e){
        this.$emit('formSubmit', this.wordToTranslate); //sending typed input to app.vue component
        e.preventDefault();
      }
  }
}
</script>

<style scoped>
.input-group-prepend {
  margin-left: 200px !important;
}
</style>
