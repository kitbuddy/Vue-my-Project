<template>
  <div>
      <modalComponent></modalComponent>

<div class="main-card">

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
  
  </div>
</template>
<script>
export default {
  props: {},
  data() {
    return {};
  },
  methods: {
    changeTitle: function() {
      this.$emit("changeTitle", "Vue Ninjas");
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
</style>