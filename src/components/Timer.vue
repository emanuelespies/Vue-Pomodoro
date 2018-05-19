<template>
    <!-- our template -->
  <section id="app" class=" is-info is-fullheight is-bold">
      <div class="container has-text-centered">
        <h1 class="title is-6">{{title}}</h1>
        
        <div id="timer">
          <span id="minutes">{{ minutes }}</span>
          <span id="middle">:</span>
          <span id="seconds">{{ seconds }}</span>
        </div>

        <div id="buttons">
      <!--     Start TImer -->
          <button 
            id="start" 
            class="button is-dark is-large" 
            v-if="!timer"
            @click="startTimer">
              <i class="far fa-play-circle"></i>
          </button>
      <!--     Pause Timer -->
          <button 
            id="stop" 
            class="button is-dark is-large" 
            v-if="timer"
            @click="stopTimer">
              <i class="far fa-pause-circle"></i>
          </button>
      <!--     Restart Timer -->
          <button 
            id="reset" 
            class="button is-dark is-large" 
            v-if="resetButton"
            @click="resetTimer">
              <i class="fas fa-undo"></i>
          </button>
        </div>
      </div>
  </section>
</template>

<script>
export default {
  name: "Timer",
  data() {
    return {
      timer: null,
      totalTime: 1 * 60,
      resetButton: false,
      title: "Let the countdown begin!"
    };
  },
  methods: {
    startTimer: function() {
      this.timer = setInterval(() => this.countdown(), 1000);
      this.resetButton = true;
      this.title = "Greatness is within sight!";
    },
    stopTimer: function() {
      clearInterval(this.timer);
      this.timer = null;
      this.resetButton = true;
      this.title = "Never quit, keep going!";
    },
    resetTimer: function(over) {
      this.totalTime = 1 * 60;
      clearInterval(this.timer);
      this.timer = null;
      this.resetButton = false;
      this.title = "Let the countdown begin!!";
      return over === true
        ? (this.title = "Good Work! Let the countdown begin again!")
        : "";
    },
    padTime: function(time) {
      return (time < 10 ? "0" : "") + time;
    },
    countdown: function() {
      return this.totalTime > 0 ? this.totalTime-- : this.resetTimer(true);
    }
  },
  computed: {
    minutes: function() {
      const minutes = Math.floor(this.totalTime / 60);
      return this.padTime(minutes);
    },
    seconds: function() {
      const seconds = this.totalTime - this.minutes * 60;
      return this.padTime(seconds);
    }
  }
};
</script>


<style lang="scss" scoped>
@import "../assets/css/timer.scss";
</style>
