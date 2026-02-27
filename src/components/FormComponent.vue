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
const startingBalance = ref(0)
const RunningBalanceHistory = ref([0])
const RunningBalance = ref(0)
const startingBalanceSwitch = ref(0)

function enterBalance() {
    // if win
    if (startingBalanceSwitch.value != 0) {
        const computedValue = Number(startingBalance.value)/4
        const computedValueSolid = Number(RunningBalanceHistory.value.at(-1)) + computedValue
        RunningBalanceHistory.value.push(computedValueSolid)
    } else {
        startingBalanceSwitch.value += 1
        RunningBalance.value = Number(startingBalance.value)
        RunningBalanceHistory.value.push(Number(startingBalance.value))
    }
    // if lose
    // computedValue = RunningBalance.value + startingBalance.value - startingBalance.value
}

function reset() {

}

const myDataValue = ref([])

</script>

<template>
    <p>What is your starting balance?: </p>
    {{ startingBalance }}
    <main class="container">
        <input class="special" v-model="startingBalance" placeholder="What is your starting Balance?"/>
    </main>
    <main class="container">
        <button v-on:click="enterBalance">Confirm-Starting Balance</button>
    </main>
    <br>
    Starting balance is:
    {{ startingBalance }} <br>
    Running balance is: {{ RunningBalanceHistory }} <br>
    {{ listOfResults }}
    {{ listOfResults2 }}

</template>

<style scoped>
.special {
    width: 19%;
}
</style>
