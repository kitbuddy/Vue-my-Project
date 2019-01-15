<template>

  <section>

  <transition name="modal" v-if="showModal"> 
   
 <div class="modal-mask">
    <button v-on:click="close()">TEST</button>
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
        </div>
      </div>
    </div>
  </transition>
  </section>

</template>

<script>
import Vue from "vue";

Vue.component("modalComponent", {});
export default {
  name: "modalComponent",
  props: [],
  mounted() {},
  data() {
    return {
      showModal: true,
      showmask: false
    };
  },
  methods: {
    close() {
      this.showModal = false;
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