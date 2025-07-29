<script setup>
import Footer from "./components/Footer.vue";
import Header from "./components/Header.vue"
import Counter from "./components/Counter.vue";

const nickname = "Giovanni Pasini"

function hello(){
  console.log("ciao")
}

</script>

<template>
  <main>
    <Header title="Nuovo Contenuto"/>
    <h1>Vue App</h1>
    <h2>{{ nickname }}</h2>

    <button v-on:click="hello">Premi!</button> 
    <button @click="hello">Premi!</button> 
    <!-- si può scrivere anche solo @ al posto di v-on -->
     <Counter />

    <Footer title="Nuovo Contenuto" owner="Me!"/>
  </main>
</template>

<style scoped></style>
