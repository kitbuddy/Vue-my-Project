<template>
    <div>
        <app-header v-bind:title="title" v-on:changeTitle="updateTitle($event)"></app-header>
       <main-card/>
        <app-footer v-bind:title="title"></app-footer>
        <modal-component> This is modal component </modal-component> 
    </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import HeaderWorld from "./components/HeaderWorld.vue";
import FooterWorld from "./components/FooterWorld.vue";
import cardComponent from "./components/cardComponent.vue";
// import Ninjas from "./components/Ninjas.vue";
// import BootstrapVue from "bootstrap-vue";
// import Vue from "vue";
// import ImageInfo from "./components/ImageInfo.vue";
import modalComponent from "./components/modalComponent.vue";

export default {
  name: "app",
  components: {
    "app-header": HeaderWorld,
    "app-footer": FooterWorld,
    // "app-ninjas": Ninjas,
    "main-card": cardComponent,
    modalComponent,
    // ImageInfo
    // HelloWorld
  },

  data() {
    return {
      ninjas: [
        { name: "Ryu", speciality: "Vue Components", show: false },
        { name: "Crystal", speciality: "HTML Wizardry", show: false },
        { name: "Hitoshi", speciality: "Click Events", show: false },
        { name: "Tango", speciality: "Conditionals", show: false },
        { name: "Kami", speciality: "Webpack", show: false },
        { name: "Yoshi", speciality: "Data Diggin", show: false }
      ],
      title: "vue-test-app"
    };
  },
  methods: {
    updateTitle: function(updatedTitle) {
      this.title = updatedTitle;
    }
  }
};
</script>

<style>
body {
  margin: 0;
  font-family: "Nunito SemiBold";
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
