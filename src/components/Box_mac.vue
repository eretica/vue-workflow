<template>
  <div class="hello">
    <div id="mydiv"
         @mousedown="dragMouseDown"
         @mouseup="dragMouseUp"
         v-bind:style="{top: top + 'px' , left: left + 'px'}">
      <div id="mydivheader">
        <div class="window">
          <div class="titlebar">
            <div class="buttons">
              <div class="close">
<<<<<<< HEAD
                <a class="closebutton" href="#" @click="delete_emit"><span><strong>x</strong></span></a>
=======
                <a class="closebutton" href="#"><span><strong>x</strong></span></a>
>>>>>>> 2db22db076c403fd6db25c27e85c3cab92e97220
                <!-- close button link -->
              </div>
              <div class="minimize">
                <a class="minimizebutton" href="#"><span><strong>&ndash;</strong></span></a>
                <!-- minimize button link -->
              </div>
              <div class="zoom">
                <a class="zoombutton" href="#"><span><strong>+</strong></span></a>
                <!-- zoom button link -->
              </div>
            </div>
            CSS OS X Yosemite Window
            <!-- window title -->
          </div>
          <div class="content">
            <h3>Hey! What's up?</h3>
            I'm a simple OS X Yosemite style window.
            <!-- window content -->
          </div>
        </div>

      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Box_mac',
  props: {
    'init_id': {type: Number},
    'ini_name': {type: String},
    'ini_top': {type: Number},
    'ini_left': {type: Number}
  },
  data () {
    return {
      id: this.init_id,
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
    delete_emit: function () {
        this.$emit('delete', this.id);
    },
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
  /*padding: 10px;*/
  cursor: move;
  z-index: 10;
  /*background-color: #2196F3;*/
  color: #fff;
}

/* ©2015 Johannes Jakob
  Made with <3 in Germany */

body {
  background: #ecf0f1;
  color: #000;
  font-family: HelveticaNeue, 'Helvetica Neue', 'Lucida Grande', Arial, sans-serif;
}

/* window BEGIN */

a {
  text-decoration: none;
}

span {
  line-height: 9px;
  vertical-align: 50%;
}

.window {
  background: #fff;
  width: 30vw;
  height: 40vh;
  margin: auto;
  /*margin-top: 12.5vh;*/
  border: 1px solid #acacac;
  border-radius: 6px;
  box-shadow: 0px 0px 20px #acacac;
}

.titlebar {
  background: -webkit-gradient(linear, left top, left bottom, color-stop(0.0, #ebebeb, color-stop(1.0, #d5d5d5)));
  background: -webkit-linear-gradient(top, #ebebeb, #d5d5d5);
  background: -moz-linear-gradient(top, #ebebeb, #d5d5d5);
  background: -ms-linear-gradient(top, #ebebeb, #d5d5d5);
  background: -o-linear-gradient(top, #ebebeb, #d5d5d5);
  background: linear-gradient(top, #ebebeb, #d5d5d5);
  color: #4d494d;
  font-size: 11pt;
  line-height: 20px;
  text-align: center;
  width: 100%;
  height: 20px;
  border-top: 1px solid #f3f1f3;
  border-bottom: 1px solid #b1aeb1;
  border-top-left-radius: 6px;
  border-top-right-radius: 6px;
  user-select: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  -o-user-select: none;
  cursor: default;
}

.buttons {
  padding-left: 8px;
  padding-top: 3px;
  float: left;
  line-height: 0px;
}

.buttons:hover a {
  visibility: visible;
}

.close {
  background: #ff5c5c;
  font-size: 9pt;
  width: 11px;
  height: 11px;
  border: 1px solid #e33e41;
  border-radius: 50%;
  display: inline-block;
}

.close:active {
  background: #c14645;
  border: 1px solid #b03537;
}

.close:active .closebutton {
  color: #4e0002;
}

.closebutton {
  color: #820005;
  visibility: hidden;
  cursor: default;
}

.minimize {
  background: #ffbd4c;
  font-size: 9pt;
  line-height: 11px;
  margin-left: 4px;
  width: 11px;
  height: 11px;
  border: 1px solid #e09e3e;
  border-radius: 50%;
  display: inline-block;
}

.minimize:active {
  background: #c08e38;
  border: 1px solid #af7c33;
}

.minimize:active .minimizebutton {
  color: #5a2607;
}

.minimizebutton {
  color: #9a5518;
  visibility: hidden;
  cursor: default;
}

.zoom {
  background: #00ca56;
  font-size: 9pt;
  line-height: 11px;
  margin-left: 6px;
  width: 11px;
  height: 11px;
  border: 1px solid #14ae46;
  border-radius: 50%;
  display: inline-block;
}

.zoom:active {
  background: #029740;
  border: 1px solid #128435;
}

.zoom:active .zoombutton {
  color: #003107;
}

.zoombutton {
  color: #006519;
  visibility: hidden;
  cursor: default;
}

.content {
  padding: 10px;
}

/* window END */

/* content BEGIN */

h3 {
  margin-top: 0px;
}

/* content END */
</style>
