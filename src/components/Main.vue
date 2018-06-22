<template>
  <div class="main">
    <button @click="add_component">クリックするとドラッグできる何かが追加されるよ！</button>

    <box-component v-for="n in count" :key="n"
                   :ini_name="'Component No.' + n"
                   :ini_top="300 + 10.5 * n"
                   :ini_left="10 + 10.5 * n">
    </box-component>

  </div>
</template>

<script>
  // import BoxComponent from '@/components/Box.vue'
  import BoxComponent from '@/components/Box_mac.vue'

  export default {
    name: 'Main',
    components: { BoxComponent },
    template: '<box-component>',
    data () {
      return {count: 1};
    },
    methods: {
      add_component: function () {
        this.count++;
      }
    }
  }
</script>

<style scoped>


</style>
