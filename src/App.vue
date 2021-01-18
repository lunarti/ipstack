<template>
  <div class="card text-center m-3">
    <h5 class="card-header">GET Request Ipstack Axios Vue</h5>
    <div class="card-body">Geo Info: {{GeoInfo}}</div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: "get-request",
  data() {
    return {
      GeoInfo: null,
      errorMessage: null
    };
  },
  created() {
    // Simple GET request using axios 
    axios.get('http://api.ipstack.com/189.37.65.210?access_key=2b5361b17468b3dc0664c269703cc043')
      .then(response => this.GeoInfo = response)
      .catch(error => {
        this.errorMessage = error.message;
        console.error("There was an error!", error);
  });
}
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
