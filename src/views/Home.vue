<template>
  <div class="home">
    <input type="text" v-model="search" />
    <p>Search term - {{ search }}</p>
    <div v-for="skill in skills" :key="skill">{{ skill }}</div>
  </div>
  <!-- <div >
    <p ref="p">
      <h1>Hello {{ personOne.name }}</h1>
      Hi, my name is {{ personOne.name }} and I am {{ personOne.age }}
    </p>
    <input v-model="personOne.name" type="text" />
    <button @click="handleClick">Name</button>
    <button @click="personOne.age++">+</button>
    <br />
    <h1>Reactive</h1>
    <p>{{ personTwo.name }} - {{ personTwo.age }}</p>
    <button @click="handleChange">Name</button>
  </div> -->
</template>

<script setup>
import { ref, reactive, computed } from "vue";

const personOne = ref({ name: "Pedro", age: 37 });
const personTwo = reactive({ name: "Terry", age: 25 });

const skills = ["css", "html", "javascript"];

const search = ref("");

const job = computed(() => {
  return { role: "developer", skills: ["css", "html", "javascript"], xp: 5 };
});

const p = ref(null);

function handleClick() {
  personOne.value.name = "Gilbert";
}
function handleChange() {
  personTwo.name = "Gilbert";
}
</script>
