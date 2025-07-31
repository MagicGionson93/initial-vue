<script setup>
import { ref } from "vue";
import { reactive, computed } from "vue";

const counter = ref(0);

function decrease() {
  --counter.value;
}

function increase() {
  ++counter.value;
}

const state = reactive({ count: 100 });

const label = ref("Prova Label");

function decreaseStateCount() {
  --state.count;
}

const computedCountLimit = computed(() => {
  return state.count < 90 ? "Limite superato" : "Perfetto";
});

function computedcountLimitFn(){
    return state.count < 90 ? "Limite superato" : "Perfetto";
}

</script>

<template>
  <div>
    <section>
      <button @click="decrease()">- decrementa</button>
      <button @click="++counter">+ incrementa</button>
      <p>Counter: {{ counter }}</p>
    </section>
    <section>
      <button @click="label = 'Nuovo Valore '">Altera Label</button>
      <div>Label: {{ label }}</div>
    </section>
    <section>
      <h2>Stato reattivo con reactive</h2>
      <button @click="decreaseStateCount">Decrementa count</button>
      <button @click="state.count++">Incrementa count</button>
      <div>Count: {{ state.count }}</div>
      <div>Stato: {{ computedCountLimit }}</div>
    </section>
  </div>
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
