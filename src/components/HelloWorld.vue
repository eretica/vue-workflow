<template>
  <div class="hello">
    <div id="mydiv"
         @mousedown="dragMouseDown"
         @mouseup="dragMouseUp"
         v-bind:style="{top: position.top + 'px' , left: position.left + 'px'}">
      <div id="mydivheader">
        Content
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
  name: 'HelloWorld',
  data () {
    return {
      offsetX: 0,
      offsetY: 0,
      position: {
        top: '500',
        left: '0',
      },
      dragg: false
    }
  },
  created: function () {
    window.addEventListener('mousemove', this.elementDrag);
  },
  methods: {
    dragMouseDown: function (e) {
      this.offsetX = e.clientX - this.position.left;
      this.offsetY = e.clientY - this.position.top;
      this.dragg = true;
    },
    dragMouseUp: function (e) {
      this.dragg = false
    },
    elementDrag: function (e) {
      if (!this.dragg) {
        return;
      }
      this.position.top = e.clientY - this.offsetY;
      this.position.left = e.clientX - this.offsetX;
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
