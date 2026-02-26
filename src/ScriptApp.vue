<script setup>
import { ref } from 'vue'
const myCount = ref(0)
const listOfAvailableOptions = [2, 3, 3, 4, 4, 4, 5, 5, 5, 5, 6, 6, 6, 6, 6,
7, 7, 7, 7, 7, 7, 8, 8, 8, 8, 8, 9, 9, 9, 9, 10, 10, 10, 11, 11, 12]
const listOfAvailableOptionsInAnotherFormat = [[1, 1], [1, 2], [2, 1], [1, 3], [2, 2], [3, 1], [1, 4], [2, 3], [3, 2], [4, 1],  [1, 5], [2, 4], [3, 3], [4, 2], [5, 1], [1, 6], [2, 5], [3, 4], [4, 3], [5, 2], [6, 1], [2, 6], [3, 5], [4, 4], [5, 3], [6, 2],  [3, 6], [4, 5], [5, 4], [6, 3], [4, 6], [5, 5], [6, 4], [5, 6], [6, 5], [6, 6]] 

const overallValueAndResult = ref(0)
const randomIndex = ref(0)
const listOfResults = ref([])
const listOfResults2 = ref([])

function add() {
  myCount.value += 1
  randomIndex.value = Math.floor(Math.random()*listOfAvailableOptions.length)
  overallValueAndResult.value = listOfAvailableOptions[randomIndex.value]
  listOfResults.value.push(overallValueAndResult.value)
  listOfResults2.value.push(listOfAvailableOptionsInAnotherFormat[randomIndex.value])
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
    {{ listOfResults }} <br>
    {{ listOfResults2 }}
  </p>
  <button v-on:click = "reset">Button-Click---Reset</button>

</template>

<style scoped>
</style>
