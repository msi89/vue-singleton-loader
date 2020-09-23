<template>
  <div id="app">
    <h1>Skeleton loader</h1>

    <img alt="Vue logo" src="./assets/logo.png" width="25%">

    <h2>Dark mode</h2>
    <div class="flex black">
      <Skeleton width="160px" height="160px" background="rgba(255, 255, 255, 0.2)"/>
      <div class="flex-desc">
        <Skeleton width="50%" background="rgba(255, 255, 255, 0.2)"/>
        <Skeleton width="80%" background="rgba(255, 255, 255, 0.2)"/>
        <Skeleton width="90%" background="rgba(255, 255, 255, 0.2)"/>
        <Skeleton width="80%" background="rgba(255, 255, 255, 0.2)"/>
        <Skeleton width="20%" background="rgba(255, 255, 255, 0.2)"/>
      </div>
    </div>
    <h2>Light mode</h2>
    <div class="flex" v-for="n in 5" :key="n">
      <Skeleton width="160px" height="160px"/>
      <div class="flex-desc">
        <Skeleton width="50%"/>
        <Skeleton width="80%"/>
        <Skeleton width="90%"/>
        <Skeleton width="80%"/>
        <Skeleton width="20%"/>
      </div>
    </div>
  </div>
</template>

<script>
import Skeleton from "./components/Skeleton";

export default {
  name: "App",
  components: {
    Skeleton
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.flex {
  display: flex;
  width: 100%;
  margin: 20px;
}

.flex-desc {
  flex: 1;
  margin-left: 10px;
}

.black {
  background-color: #000;
}
</style>
