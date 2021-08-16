<template>
  <div id="app">
    <major-clock :second="second1" :minute="minute" :hour="hour1"/>
    <control-buttons v-model="hour1"/>
    <split-times/>
  </div>
</template>

<script>
import ControlButtons from './components/ControlButtons.vue'
import MajorClock from './components/MajorClock.vue'
import SplitTimes from './components/SplitTimes.vue'
export default {
  name: 'App',
  components: {
    MajorClock,
    ControlButtons,
    SplitTimes

  },
  data () {
    return {
      hour1: 0,
      minute1: 0,
      second1: 0,
    }
  }
}
</script>

<style>
#app {
  width: 300px;
  height: 700px;
  margin: 0 auto;
  padding: 0 30px;
  background-color: #000;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
