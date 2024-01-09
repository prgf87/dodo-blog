<template>
  <router-view />
</template>

<style>
* {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background: #2c3e50;
  color: blanchedalmond;
}

/* nav {
  padding: 20px;
}

nav a {
  font-weight: bold;
  font-size: 16px;
  background: #555;
  padding: 8px 16px;
  border-radius: 4px;
}

nav a:hover {
  background-color: #4e6174;
} */

nav a.router-link-exact-active {
  color: #f83434;
}
</style>
