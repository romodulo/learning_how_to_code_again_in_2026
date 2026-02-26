// This test works
<script setup>
import { ref } from 'vue'
const myCount = ref(0)

function add() {
  myCount.value += 1
}

</script>

<template>
  <p>
    {{ myCount }}
  </p>  

  <button v-on:click = "add">Button-Click</button>
  <p>
    new comp
  </p>
</template>

<style scoped>
</style>
