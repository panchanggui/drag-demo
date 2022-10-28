<template>
  <div class="drag">
    <!-- <h1>Draggabilly v3 - with vanilla JS</h1> -->
    <div class="draggable" ref="robot"></div>
  </div>
</template>

<script>
export default {
  name: 'Drag',

  data () {
    return {

    };
  },

  mounted() {
    var Draggabilly = require('draggabilly');
    var draggie = new Draggabilly( '.draggable', {
      // options
      // containment: '.drag'
      // containment: true
      limit: (x, y) => {
        x = x > (window.innerWidth - 160) ? (window.innerWidth - 160) : x
        y = y > (window.innerHeight - 160) ? (window.innerHeight - 160) : y
        y = y < 0 ? 0 : y
        x = x < 0 ? 0 : x
        return {
          x,
          y,
        }
      },
    });

    /* this.$nextTick(function () {
      const drag = require('../plugins/draggable.min.js')
      this.drag = new drag(this.$refs.robot, {
        // setPosition: false,
        limit: (x, y) => {
          x = x > (window.innerWidth - 160) ? (window.innerWidth - 160) : x
          y = y > (window.innerHeight - 160) ? (window.innerHeight - 160) : y
          y = y < 0 ? 0 : y
          x = x < 0 ? 0 : x
          return {
            x,
            y,
          }
        },
      })
    }); */


    
  },



  methods: {

    

  }

}
</script>

<style lang='scss' scoped>
.drag {
  // background-color: red;
  // padding: 10px;
  // border: 2px solid #F90;
  // height: 100%;
  // width: 100%;
  // background-size:100%;
  position: fixed;
  top: 10px;
  left: 10px;
  bottom: 10px;
  right: 10px;
  


  .draggable {
  width: 140px;
  height: 140px;
  background: #F90;
  border-radius: 10px;
  cursor: move;
  z-index: 9999;
  position: absolute;
  float: right;
  bottom: 120px;
  right: 50px;
}
.draggable.is-pointer-down {
  background: #09F;
  // width: 340px;
}
.draggable.is-dragging { opacity: 0.7; }
}

</style>