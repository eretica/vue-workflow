<template>
  <div class="hello">
    <button @click="add_component">Add Component</button>

    <box-component v-for="n in count"></box-component>

  </div>
</template>

<script>
  import BoxComponent from './box.vue';

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
