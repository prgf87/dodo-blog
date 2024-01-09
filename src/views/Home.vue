<template>
  <div class="home">
    <input type="text" v-model="search" />
    <p>Search term - {{ search }}</p>
    <!-- <div v-for="skill in skills" :key="skill">{{ skill }}</div> -->
    <div v-for="match in matches" :key="match">{{ match }}</div>
    <button @click="handleClick">stop watching</button>
  </div>
</template>

<script setup>
import { ref, reactive, computed, watch, watchEffect } from "vue";

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

function handleClick() {
  stopWatch();
  stopEffect();
}
</script>
