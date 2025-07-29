<script setup>

import { ref } from "vue";
const counter = ref(0)

function decrease() {
    --counter.value;
}

function increase() {
    ++counter.value;
}

</script>
<template>
    <section>
        <button @click="decrease()">- decrementa</button>
        <button @click="increase()">+ incrementa</button>
        <p>{{ counter }}</p>
    </section>
</template>

<style scope>
section {
    padding: 20px;
    background-color: lightblue;
    margin: 20px 0;
}

button {
    padding: 6px;
    background-color: blueviolet;
    border-radius: 6px;
}
</style>