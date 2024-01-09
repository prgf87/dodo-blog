<template>
  <div class="home">
    <input type="text" v-model="search" />
    <p>Search term - {{ search }}</p>
    <!-- <div v-for="skill in skills" :key="skill">{{ skill }}</div> -->
    <div v-for="match in matches" :key="match">{{ match }}</div>
    <button @click="handleClick">stop watching</button>
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
import { ref, reactive, computed, watch, watchEffect } from "vue";

const personOne = ref({ name: "Pedro", age: 37 });
const personTwo = reactive({ name: "Terry", age: 25 });

const skills = ref(["css", "html", "javascript"]);

const search = ref("");

const stopWatch = watch(search, () => {
  console.log("watched");
});

const stopEffect = watchEffect(() => {
  console.log("watchEffect", search.value);
});

const matches = computed(() => {
  return skills.value.filter((skill) => skill.includes(search.value));
});

// const job = computed(() => {
//   return { role: "developer", skills: ["css", "html", "javascript"], xp: 5 };
// });

const p = ref(null);

function handleClick() {
  stopWatch();
  stopEffect();
}
// function handleChange() {
//   personTwo.name = "Gilbert";
// }
</script>
