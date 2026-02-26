<script setup>
import ScriptApp from './ScriptApp.vue'
import BaccaratScript from './components/BaccaratScript.vue';
import FormComponent from './components/FormComponent.vue'

</script>

<template>
  <h1>You did it!</h1>
  <p>
    Will this still work &ltdelete-later--paragraph-tag&gt ?
  </p>
  <p>
    This link only goes to <a href="https://vuejs.org/" target="_blank" rel="noopener">www.google.com</a>
    .
  </p>
  <p>
    Welcome to guam-directory.com
  </p>
  <!-- break -->
  <p>
    New App mounted:
  </p>
  <!-- end-OfBreak -->
  <!-- break -->
  <br>
  <ScriptApp />
  <!-- end-OfBreak -->
  <!-- break -->
  <br>
  <BaccaratScript />
  <!-- end-OfBreak -->
  <!-- break -->
  <br>
  <FormComponent />
  <!-- end-OfBreak -->
</template>

<style scoped>
</style>
