<template>
  <div class="box">
    <button @click="degree">计次</button>
    
    <button @click="launch">启动</button>
  </div>
</template>
<script>
export default {
  name: 'control-buttons',
  props: {
    value: {
      type:Number,
      default: 0
    },
    frequency: {
      type: Number,
      default: 1
    }
  },
  data () {
    return {
      val:this.value
    }
  },
  watch: {
    val: function (newValue) {
      this.$emit('input', newValue)
    },
    value: function (newValue) {
      this.val = newValue
    }
  },
  mounted () {
    this.conversion()
  },
  methods: {
    launch () {
      setInterval(() => {
        console.log(11);
        this.val++
      }, 1000)
    },
    conversion () {
      if (this.val == 60) {
        this.val = 0
      }
    },
    degree () {
    }
  }
}
</script>
<style>
.box{
  display: flex;
  justify-content: space-between;
}
button{
  width: 70px;
  height: 70px;
  color: #fff;
  border-radius: 100%;
  border: 1px solid rgb(163, 163, 163);
  background-color: rgba(185, 184, 184,.3);
}
</style>