<script setup>
import { ref } from 'vue'
const myCount = ref(0)
const listOfAvailableOptions = ["B", "P"]
const overallValueAndResult = ref(0)
const randomIndex = ref(0)
const listOfResults = ref([])

function add() {
  myCount.value += 1
  randomIndex.value = Math.floor(Math.random()*listOfAvailableOptions.length)
  overallValueAndResult.value = listOfAvailableOptions[randomIndex.value]
  listOfResults.value.unshift(overallValueAndResult.value)
}

function reset() {
  myCount.value = 0
  myDataValue.value = []
  listOfResults.value = []
}

const myDataValue = ref([])

</script>

<template>
  <p>
    My count is:
    {{ myCount }}
  </p>
  <button v-on:click = "add">Button-Click</button>
  <p>
    {{ listOfResults }}
  </p>
  <button v-on:click = "reset">Button-Click---Reset</button>

</template>

<style scoped>
</style>
