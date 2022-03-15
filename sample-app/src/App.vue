<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <SampleComponent msg="Sample Text" />
    <CounterComponent />
    <HelloWorld msg="Hello World!!" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import SampleComponent from "./components/SampleComponent.vue";
import CounterComponent from "./components/CounterComponent.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    SampleComponent,
    CounterComponent,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
