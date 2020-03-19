<template>
  <div id="wordOutput">
         <h4 class="bg-dark text-white">{{ wordTranslated }}</h4>
  </div>
</template>

<script>


export default {
  name: 'wordOutput',
  props: {
      wordTranslated : String 
   }
}
</script>

<style scoped>

</style>