<script setup>
    // const props = defineProps([
    //     "text", "owner"
    // ])
    const props = defineProps({
        text: String,
        owner: {
            type: String,
            required: true,
        }
    })
</script>

<template>
    <footer>
        {{ text }}
        <div>
            Copyright of {{ owner }}
        </div>
    </footer>
</template>

<style scoped>
footer{
    padding: 10px;
    background-color: lightcoral;
    color: black;
}
</style>