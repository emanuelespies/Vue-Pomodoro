<template>
  <div id="app">
    <HelloWorld/>
    <Timer />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import Timer from "./components/Timer";

export default {
  name: "App",
  components: {
    HelloWorld,
    Timer
  }
};
</script>


<style lang="scss">
@import "./assets/css/main.scss";
@import "./assets/css/app.scss";
</style>
