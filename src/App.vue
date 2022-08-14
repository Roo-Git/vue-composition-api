<template>
  <section class="container">
    <h1>Values</h1>
    <h2>{{ uNameValue }}</h2>
    <h3>{{ userAge }}</h3>
    <button @click="newAgeValue">Change Age</button>
    <div>
      <input type="text" placeholder="firstname" v-model="firstName" />
      <input type="text" placeholder="lastname" v-model="lastName" />
    </div>
  </section>
  <section class="container">
    <h1>Objects</h1>
    <h2>{{ uNameObj }}</h2>
    <h3>{{ user.age }}</h3>
    <button @click="newAgeObj">Change Age</button>
    <div>
      <input type="text" placeholder="firstname" v-model="user.firstName" />
      <input type="text" placeholder="lastname" v-model="user.lastName" />
    </div>
  </section>
</template>

<script setup>
import { reactive, ref, computed } from "vue";

// Values
const firstName = ref("");
const lastName = ref("");
const userAge = ref(31);

// Objects
const user = reactive({
  userName: "Silver",
  firstName: "",
  lastName: "",
  age: 31,
});

// Methods
function newAgeValue() {
  return userAge.value++;
}

function newAgeObj() {
  return user.age++;
}

// Computed

const uNameValue = computed(function () {
  return `${firstName.value} ${lastName.value}`;
});

const uNameObj = computed(function () {
  return `${user.firstName} ${user.lastName}`;
});

//
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
