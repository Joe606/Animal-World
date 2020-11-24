<template>
  <div id="app">
    <div id="nav">
    <h1>Animal world</h1>
    <nav>
    
      <span class="thesame">species</span>
     <span class="thesame"> amount </span>
      <span class="thesame">distribution </span>
      <span class="thesame">food </span>
    
    </nav>
      <router-link to="/"></router-link>
    </div>
    <router-view/>
  </div>
</template>

<style>
body{
  background-color: rgb(10, 9, 9);
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c4c6d;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

#thesame{
  width: 40px;
  height: 40px;
  border: 40px;
  font-size: 40px;
}
</style>
