<template>
  <div id="wordInput">
    <form class=" mt-5" v-on:submit="formSubmit">
      <div class="input-group mb-3">
        <div class="input-group-prepend">
          <span class="input-group-text" id="basic-addon1">Word</span>
        </div>
        <input
          type="text"
          class="form-control"
          placeholder="type words here..."
          aria-label="Username"
          aria-describedby="basic-addon1"
          v-model="wordToTranslate"
        />
        <select  class="custom-select-md" v-model="language">
            <option value="fr">French</option>
            <option value="es">Spanish</option>
            <option value="zh">Chinese</option>
            <option value="de">German</option>
            <option value="it">Italian</option>
            <option value="ru">Russian</option>
            <option value="pt">Portuguese</option>
        </select>
        <input class="btn btn-success" type="submit" value="Translate">
      </div>
    </form>
     <h4 >preview : {{wordToTranslate}}</h4>
     <div class="my-4 text-capitalize">
         <span class="underline" >Translation is shown below :</span> 
     </div>
  </div>
</template>

<script>
export default {
  name: "wordInput",
  data(){
      return {
          wordToTranslate: '',
          language: ''
      }
  },
  created(){
      this.language = 'fr';
  },
  methods : {
      formSubmit(e){
        this.$emit('formSubmit', this.wordToTranslate, this.language); //sending typed input to app.vue component
        e.preventDefault();
      }
  }
}
</script>

<style scoped>
.underline {
  border-bottom: 3px solid rgb(168, 229, 168);
  color: rgb(168, 229, 168);
  font-size: 20px;
}

</style>
