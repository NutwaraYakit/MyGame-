<template>
  <div id="app">
    <img  src="./assets/1.jpg" width="100%" height="60%" />
    <HelloWorld msg="Random character" />
    <br />
    <br />
    <div>
      <botton />
    </div>
    <footer class="my-0 pt-0 text-muted text-center text-small">
        <p class="mb-0">&copy; Nutwara Yakit 6104101346</p>
    </footer>
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
  background-color: black;
  height: 100%;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  position: relative;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: rgb(255, 255, 255);
}

</style>
