<script setup>

import { ref } from 'vue';

    const showDiv1 = ref(true)

    function toogleDiv1(){
        showDiv1.value = !showDiv1.value
    }

    const color = "red"

</script>
<template>
  <div>
    <h1>Vue App 3</h1>
    
    <div v-if="showDiv1">Questo contenuto è mostrato in modo condizionato</div>
    <div v-else>Contenuto alternativo mostrato</div>
    <button @click="toogleDiv1">Toogle Div1</button>
    
    <section>

        <div v-if="color == 'red'">Color: rosso</div>
        <div v-else-if="color == 'blue'">Color: blu</div>

    </section>

    </div>
</template>

<style scoped>

    section{
        margin: 20px 0;
    }

</style>