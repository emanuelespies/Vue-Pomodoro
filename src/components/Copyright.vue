<template>
  <footer>
    <small>{{ msg }} - {{ new Date().getFullYear() }} - 
    <a v-bind:href="''+link+''">
      {{linkText}}
    </a>
    </small>
  </footer>
</template>


<script>
export default {
  name: "Copyright",
  data() {
    return {
      msg: "@emanuelespies",
      link: "https://github.com/emanuelespies/Vue-Pomodoro",
      linkText: "GitHub Repository"
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
footer {
  text-align: left;
  position: fixed;
  bottom: 15px;
}
small {
  color: #444;
  font-size: 12px;
}
</style>
