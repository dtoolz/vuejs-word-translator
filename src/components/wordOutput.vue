<template>
  <div id="wordOutput">
     <div class="container">
         <h4 class="my-3">{{ wordTranslated }}</h4>
     </div>
  </div>
</template>

<script>


export default {
  name: 'wordOutput',
  props: ['wordTranslated']
}
</script>

<style scoped>

</style>