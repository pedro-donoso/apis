<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Jsonplaceholder</router-link> |
      <router-link to="/Randomuser">Randomuser</router-link>
    </div>
    <router-view/>
  </div>
</template>

<style lang="scss">
#app{
  text-align: center;
  font-family: 'Courier New', Courier, monospace;
  color:blue;
}

</style>
