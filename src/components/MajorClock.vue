<template>
  <div class="second-chronograph">
      <span>{{second}}</span>
      <a>:</a>
      <span>{{minute}}</span>
      <a>:</a>
      <span>{{hour}}</span>
    </div>
</template>

<script>
export default {
  name: 'major-clock',
  props: {
    second: {
      type: Number,
      default: 0
    },
    minute: {
      type: Number,
      default: 0
    },
    hour: {
      type: Number,
      default: 0
    },
  },
  data () {
    return {
      val: this.value
    }
  },
  watch: {
    val: function (newValue) {
      this.$emit('input', newValue)
    },
    value: function (newValue) {
      this.val = newValue
    }
  }
}
</script>

<style>
.second-chronograph{
  display: flex;
  justify-content: space-around;
}
span{
  font-size: 80px;
  color: #fff;
  font-weight: normal;
}
a{
  font-size: 80px;
  color: #fff;
}
</style>