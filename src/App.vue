<template>
  <div id="app">
    <br />
    <img class="rounded-circle" src="./assets/2.jpg" width="20%" />
    <HelloWorld msg="Nonog_Narlux" />
    <br />
    <h1 class="text-light">---------------- Narlux Battle Fighters ----------------</h1>
    <div>
      <botton />
    </div>
  </div>
</template>
<script>
import HelloWorld from "./components/HelloWorld.vue";
import botton from "./components/botton.vue";
export default {
  name: "App",
  components: {
    HelloWorld,
    botton,
  },
};
</script>

<style>
#app {
  background-image: url(https://cdn.pixabay.com/photo/2015/11/11/03/47/evening-1038148_1280.jpg);
  height: 100%x;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  position: relative;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
