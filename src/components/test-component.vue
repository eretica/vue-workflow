<template>
  <div>
    A custom component!
    <button class="hoge-red" @click="hoge_alert">aaa</button>
  </div>
</template>

<script>
export default {
  name: 'TestComponent',
  data () {
    return {
    }
  },
  methods: {
    hoge_alert: function () {
      alert('hi');
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .hoge-red {
    color: darkred;
  }
</style>
