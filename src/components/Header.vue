<script setup>
const props = defineProps([
    "title"
])
</script>

<template>
    <header>
        {{ title }}
    </header>
</template>

<style scoped>
header {
    background-color: lightblue;
    padding: 10px;
    color: black;
}
</style>