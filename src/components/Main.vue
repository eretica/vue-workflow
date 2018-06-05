<template>
  <div class="hello">
    <button @click="add_component">Add Component</button>

    <box-component v-for="n in count" :key="n"
                   :ini_name="'Component No.' + n"
                   :ini_top="300 + 10.5 * n"
                   :ini_left="10 + 10.5 * n">
    </box-component>

  </div>
</template>

<script>
  import BoxComponent from '@/components/Box.vue'

  export default {
    name: 'HelloWorld',
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
