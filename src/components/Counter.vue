<template>
    <div>
        <h1>Counter: {{ counter }} <span v-if="isBelowZero()">Gone below zero</span></h1>
        <button @click="increment">Increase</button>
        <button @click="decrease">Decrease</button>
        <input type="number" v-model="counter">
    </div>
</template>

<script>
    export default {
        name: 'Counter',
        data() {
            return {
                counter: 10,
            }
        },
        methods: {
            increment() {
                this.counter = Number.parseInt(this.counter) + 1
            },
            decrease() {
                this.counter = this.counter - 1
            },
            isBelowZero() {
                return Number.parseInt(this.counter) < 0
            }
        }
    }
</script>