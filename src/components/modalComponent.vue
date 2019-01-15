<template>

  <section>
  <transition name="modal"  >
 <div class="modal-mask">
      <div class="modal-wrapper">
        <div class="modal-container">

          <div class="modal-header">
            <slot name="header">
              default header
            </slot>
          </div>

          <div class="modal-body">
            <slot name="body">
              default body
            </slot>
          </div>

          <div class="modal-footer">
            <slot name="footer">
              default footer
              <button class="modal-default-button" @click="showmask = false">
                OK
              </button>
            </slot>
          </div>
        </div>
      </div>
    </div>
  </transition>


<div id="app">
<button id="show-modal" @click="showmask = !showmask">show mask</button>
  <!-- use the modal component, pass in the prop -->
  <modal v-if="showModal" @close="showModal = false">
    <!--
      you can use custom content here to overwrite
      default content
    -->
    <div>
      this is test div
    </div>
    <h3 slot="header">custom header</h3>
  </modal>
</div>
  </section>

</template>

<script>
import Vue from "vue";

Vue.component("modalComponent", {});
export default {
  name: "modalComponent",
  props: [],
  mounted() {},
  data: function() {
    return {
      showModal: false,
      showmask: false
    };
  },
  methods: {
    hideMessage() {
      this.showModal = false;
    },
    close() {
      console.log(" this is from close button");
    }
  },
  computed: {}
};
</script>

<style scoped>
.header-main {
  height: 50px;
  background-color: gray;
  margin-top: 0%;
}


#message {
  position: absolute;
}

.modal-mask {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: table;
  transition: opacity 0.3s ease;
}

.modal-wrapper {
  display: table-cell;
  vertical-align: middle;
}

.modal-container {
  width: 300px;
  margin: 0px auto;
  padding: 20px 30px;
  background-color: #fff;
  border-radius: 2px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.33);
  transition: all 0.3s ease;
  font-family: Helvetica, Arial, sans-serif;
}

.modal-header h3 {
  margin-top: 0;
  color: #42b983;
}

.modal-body {
  margin: 20px 0;
}

.modal-default-button {
  float: right;
}

/*
 * The following styles are auto-applied to elements with
 * transition="modal" when their visibility is toggled
 * by Vue.js.
 *
 * You can easily play with the modal transition by editing
 * these styles.
 */

.modal-enter {
  opacity: 0;
}

.modal-leave-active {
  opacity: 0;
}

.modal-enter .modal-container,
.modal-leave-active .modal-container {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
}
</style>