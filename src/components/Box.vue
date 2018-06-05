<template>
  <div class="hello">
    <div id="mydiv"
         @mousedown="dragMouseDown"
         @mouseup="dragMouseUp"
         v-bind:style="{top: top + 'px' , left: left + 'px'}">
      <div id="mydivheader">
        {{ name }}
        <div>
          <input type="text">
        </div>
        <div>
          <button>👀</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Box',
  props: {
    'ini_name': {type: String},
    'ini_top': {type: Number},
    'ini_left': {type: Number}
  },
  data () {
    return {
      name: this.ini_name,
      offsetX: 0,
      offsetY: 0,
      top: this.ini_top,
      left: this.ini_left,
      dragg: false
    }
  },
  created: function () {
    window.addEventListener('mousemove', this.elementDrag);
  },
  methods: {
    dragMouseDown: function (e) {
      this.offsetX = e.clientX - this.left;
      this.offsetY = e.clientY - this.top;
      this.dragg = true;
    },
    dragMouseUp: function (e) {
      this.dragg = false
    },
    elementDrag: function (e) {
      if (!this.dragg) {
        return;
      }
      this.top = e.clientY - this.offsetY;
      this.left = e.clientX - this.offsetX;
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

#mydiv {
  position: absolute;
  z-index: 9;
  background-color: #f1f1f1;
  border: 1px solid #d3d3d3;
  text-align: center;
}

#mydivheader {
  padding: 10px;
  cursor: move;
  z-index: 10;
  background-color: #2196F3;
  color: #fff;
}
</style>
