<template>
  <div>
      <ImageInfo v-if="openImageInfo"></ImageInfo>
<div class="main-card">
<span class=" row">
       
<div class="card col-xs-6 col-sm-3">
    <div class="container"  v-on:click="showImageInfoModal()">
         <img src="../../public/images/img-2.jpg" alt="Avatar" style="width:100%" >
    <h4><b>John Doe</b></h4> 
    <p>Architect & Engineer</p> 
  </div>
</div>

<div class="card col-xs-6 col-sm-3">
    <div class="container">
         <img src="../../public/images/img-2.jpg" alt="Avatar" style="width:100%">
    <h4><b>John Doe</b></h4> 
    <p>Architect & Engineer</p> 
  </div>
</div>


<div class="card col-xs-6 col-sm-3">
    <div class="container"  @click="callmodal()">
         <img src="../../public/images/clickImage.png" alt="Avatar" style="width:100%">
    <h4><b>John Doe</b></h4> 
    <p>Architect & Engineer</p> 
  </div>
</div>
</span>

<span class=" row">
       
<div class="card col-xs-6 col-sm-3">
    <div class="container">
         <img src="../../public/images/img-2.jpg" alt="Avatar" style="width:100%">
    <h4><b>John Doe</b></h4> 
    <p>Architect & Engineer</p> 
  </div>
</div>

<div class="card col-xs-6 col-sm-3">
    <div class="container">
         <img src="../../public/images/img-2.jpg" alt="Avatar" style="width:100%">
    <h4><b>John Doe</b></h4> 
    <p>Architect & Engineer</p> 
  </div>
</div>


<div class="card col-xs-6 col-sm-3">
    <div class="container">
         <img src="../../public/images/img-2.jpg" alt="Avatar" style="width:100%">
    <h4><b>John Doe</b></h4> 
    <p>Architect & Engineer</p> 
  </div>
</div>
</span>
  </div>
  <div id="modalForItem">
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
  </div>
  </div>

  

</template>


<script>

import ImageInfo from "./ImageInfo.vue"

export default {
  props: {},
  data() {
    return {
      showModal: false,
      openImageInfo: false
    };
  },
  mounted() {
    ImageInfo
  },
    created() {
  },
  methods: {
    changeTitle: function() {
      this.$emit("changeTitle", "Vue Ninjas");
    },
    close() {
      this.showModal = false;
    },
    showImageInfoModal() {
      this.openImageInfo = true
    }
  }
};
</script>
<style scoped>
.card {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  transition: 0.3s;
  width: 30%;
  max-width: 300px;
  margin: 15px;
}

.main-card {
  align-self: center;
  align-content: flex-start;
  padding: 10px 30px;
  margin: 3% 20%;
  width: 65%;
  max-height: 70%; 
  background-color: #F8F8F8;
}

.column {
  width: 33.33%;
}

.row:after {
  content: "";
  display: table;
  clear: both;
}
.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}

.container {
  padding: 30px 8px;
}


/* this is css for modals only  */
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

/* this is css for modals only  */

</style>