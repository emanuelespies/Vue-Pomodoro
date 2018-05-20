<template>
  <div id="app">
    <!-- <HelloWorld/> the original component -->
    <Timer />
    <Copyright />
  </div>
</template>

<script>
//import HelloWorld from "./components/HelloWorld";
import Timer from "./components/Timer";
import Copyright from "./components/Copyright";

export default {
  name: "App",
  components: {
    //HelloWorld,
    Timer,
    Copyright
  }
};
</script>


<style lang="scss">
@import "./assets/css/main.scss";
@import "./assets/css/app.scss";
</style>
