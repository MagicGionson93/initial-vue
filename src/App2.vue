<script setup>
import { ref } from "vue";
import { reactive } from "vue";

const v1 = "<h2>Intestazione</h2>";
const x = 10;
const divId = x > 10 ? "box1" : "box2";

const btnDisabled = true;

const div2 = {
  title: "Titolo di div2",
  id: "div2",
  class: "box2",
};

const linkAttribute = {
  attr: "href",
  url: "https://www.google.it",
};
// const url = "https://www.google.it"

const eventObj = {
  type: "click",
  handler: () => {
    console.log("Hai premuto il pulsante!");
  },
};

const div3Class = ref("first");

function changeDiv3Class() {
  //   if (div3Class.value == "first") {
  //     div3Class.value = "second";
  //   } else {
  //     div3Class.value = "first";
  //   }

  div3Class.value = div3Class.value == "first" ? "second" : "first";
}

const secondClass = ref(true);
const thirdClass = ref(true);
const fourthClass = ref(false);

const div5Classes = reactive({
  second: true,
  third: true,
  fourth: false,
  "text-danger": true,
});

const div6Color = "lightgreen";

const div7Style = reactive({
  color: "blue",
  fontSize: "30px",
  backgroundColor: "yellow",
});

function aumentaFontSize(){
    div7Style["font-size"] = "50px"
}

const value = 100;
const message = "Vue framework"

</script>

<template>
  <div>
    <h1>Vue App 2</h1>
    <div v-html="v1"></div>
    <div v-bind:id="divId">
      <!-- Possiamo anche usare solo ":id" senza "v-bind" come shortcut -->
      Lorem, ipsum dolor sit amet consectetur adipisicing elit.
    </div>

    <button :disabled="btnDisabled">Pulsante disabilitato</button>

    <div v-bind="div2">div 2</div>

    <a :[linkAttribute.attr]="linkAttribute.url">Testo del link</a>

    <button @[eventObj.type]="eventObj.handler">Pulsante</button>

    <section>
      <div :class="div3Class">div 3</div>
      <button @click="changeDiv3Class">Toogle div3</button>
    </section>

    <section>
      <div
        :class="{ second: secondClass, third: thirdClass, fourth: fourthClass }"
      >
        Div 4 con ref
      </div>
    </section>
  </div>

  <section>
    <div :class="div5Classes">Div 5 con reactive</div>
  </section>

  <section><div :style="{ color: div6Color }">Div 6</div></section>

  <section>
    <div :style="div7Style">Div 7</div>
    <button @click="aumentaFontSize">Aumenta dimensioni testo</button>
  </section>

  <section>
    {{ value == 100 ? "red" : "blue" }}
    <div>{{ message.toUpperCase() }}</div>
    <div> {{ message.split('').reverse().join('') }}</div> 
  </section>



</template>

<style scoped>
#box1,
#box2,
#div2 {
  color: black;
  padding: 10px;
}

#box1 {
  background-color: lightcoral;
}

#box2 {
  background-color: lightgreen;
}

#div2 {
  background-color: brown;
  margin: 20px 0 0 0;
}

.box2 {
  border: 3px solid black;
}

.first {
  background-color: lightblue;
}

.second {
  background-color: lightsalmon;
}

.third {
  border: 5px solid red;
}

.fourth {
  border-radius: 20px;
}

.text-danger {
  font-size: 30px;
  color: red;
}

section {
  margin: 20px 0;
}
</style>
