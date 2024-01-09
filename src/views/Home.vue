<template>
  <div class="home">
    <h1>Hello {{ name }}</h1>
    <p ref="p">Hi, my name is {{ name }} and I am {{ age }}</p>
    <input v-model="name" type="text" />
    <button @click="age++">+</button>
  </div>
</template>

<script setup>
import { ref } from "vue";

const name = ref("Pedro");
const age = ref(55);

const p = ref(null);

function handleClick() {
  name.value = "Gilbert";
}
</script>
