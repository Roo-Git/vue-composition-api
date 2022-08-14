<template>
  <section class="container">
    <h2>{{ userName }}</h2>
    <h3>{{ userAge }}</h3>
    <button @click="newAgeValue">Change Age</button>
  </section>
  <section class="container">
    <h2>{{ user.name }}</h2>
    <h3>{{ user.age }}</h3>
    <button @click="newAgeObj">Change Age</button>
  </section>
</template>

<script setup>
import { reactive, ref } from "vue";

// Values
const userName = ref("Laura");
const userAge = ref(31);

// Objects
const user = reactive({
  name: "Robert",
  age: 31,
});

// Methods
function newAgeValue() {
  return userAge.value++;
}

function newAgeObj() {
  return user.age++;
}
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}

.container {
  margin: 3rem auto;
  max-width: 30rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 1rem;
  text-align: center;
}
</style>
