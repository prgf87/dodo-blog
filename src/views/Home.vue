<template>
  <div class="home">
    <h1>Hello {{ name }}</h1>
    <input type="text" value="name" />
    <button @click="handleClick">Change Name</button>
  </div>
</template>

<script setup>
let name = "Pedro";

function handleClick() {
  console.log("clicked!");
}
</script>
