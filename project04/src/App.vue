<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link to="/welcome">Welcome</router-link> |
    <router-link to="/databinding/string">String</router-link> |
    <router-link to="/databinding/html">Html</router-link> |
    <router-link to="/databinding/input">input</router-link> |
    <router-link to="/databinding/attr">attribute</router-link> |
    <router-link to="/event/list">List</router-link> |
    <router-link to="/event/click">click</router-link> |
    <router-link to="/event/change">Change</router-link> |
    <router-link to="/event/key">key</router-link> |
    <router-link to="/memo/list">memo</router-link>
  </nav>
  <router-view/>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
