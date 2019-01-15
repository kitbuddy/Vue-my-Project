<template>
    <header>
      <div class="d-flex flex-column flex-md-row align-items-center p-3 px-md-4 mb-3 border-bottom shadow-sm">
      <h4 class="my-0 mr-md-auto font-weight-normal">Test Company name</h4>
      <br/>
      <h5 class="my-0 mr-md-auto font-weight-normal">Test Company name</h5>
      
      <nav class="my-2 my-md-0 mr-md-3">
        <a class="p-2 text-dark" href="#">Features</a>
        <a class="p-2 text-dark" href="#">Enterprise</a>
        <a class="p-2 text-dark" href="#">Support</a>
        <a class="p-2 text-dark" href="#">Pricing</a>
      </nav>
      <a class="btn btn-outline-primary" href="#">Open Store Info</a>
    </div>
    </header>
</template>
<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    }
  },
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
header {
  background: #d0d0d0;
  /* padding: 10px; */
  max-height: 10%;
}
h1 {
  color: #222;
  text-align: center;
}
</style>