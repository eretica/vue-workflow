<template>
  <div class="hello">

    <box-component></box-component>
    <box-component></box-component>
    <box-component></box-component>

  </div>
</template>

<script>
  // import MyComponent from './test-component.vue';
  import BoxComponent from './box.vue';

export default {
  name: 'HelloWorld',
  components: { BoxComponent },
  template: '<box-component>',
  data () {
    return {};
  },
  created: function () {
  },
  methods: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

/*#mydiv {*/
  /*position: absolute;*/
  /*z-index: 9;*/
  /*background-color: #f1f1f1;*/
  /*border: 1px solid #d3d3d3;*/
  /*text-align: center;*/
/*}*/

/*#mydivheader {*/
  /*padding: 10px;*/
  /*cursor: move;*/
  /*z-index: 10;*/
  /*background-color: #2196F3;*/
  /*color: #fff;*/
/*}*/
</style>
