<template>
  <div>
    <section>
      <transition name="modal" v-if="showModal">
        <div class="modal-mask">
          <button class="close-modal" v-on:click="close()">X</button>
          <div class="modal-wrapper">
            <div class="modal-container">
              <div class="modal-header">
                <slot name="header">
                  <h1>THIS IS HEADER</h1>
                </slot>
              </div>

              <div class="modal-body">
                <slot name="body">
                  <loginComponent v-bind:userPresent="true"></loginComponent>
                </slot>
              </div>
            </div>
          </div>
        </div>
      </transition>
    </section>
  </div>
</template>

<script>
import Vue from "vue";
import loginComponent from "./loginComponent.vue";

Vue.component("modalComponent", {});
export default {
  name: "modalComponent",
  components: {
    loginComponent
  },
  props: [],
  mounted() {
    loginComponent;
  },
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
  text-align-last: auto;
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
  width: max-content !important;
  margin: 0px auto;
  background-color: whitesmoke;
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

.close-modal {
  position: absolute;
  right: 0px;
  background: rgb(0, 128, 119);
}
</style>