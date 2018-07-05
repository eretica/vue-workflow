<template>
  <div class="main">
    <button @click="add_component">クリックするとドラッグできる何かが追加されるよ！</button>

    <box-component v-for="(data, n) in count" :key="n"
                   :init_id="n"
                   :ini_name="'Component No.' + n"
                   :ini_top="300 + 10.5 * n"
                   :ini_left="10 + 10.5 * n"
                   @delete="delete_emit"

    >
    </box-component>

  </div>
</template>

<script>
  import Vue from 'vue';
  // import BoxComponent from '@/components/Box.vue'
  import BoxComponent from '@/components/Box_mac.vue'

  export default {
    name: 'Main',
    components: { BoxComponent },
    template: '<box-component>',
    data () {
      return {count: [{}]};
    },
    methods: {
      add_component: function () {
        this.count.push([{}]);
      },
      delete_emit: function (key) {
          console.log('delete...' + key);
          Vue.delete(this.count, key);
      }
    }
  }
</script>

<style scoped>


</style>
