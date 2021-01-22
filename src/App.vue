<template>
  <div class="card text-center m-3">
    <h4 class="card-header">GET Request Ipstack Axios Vue</h4>
    <div class="card-body">Ip: {{ GeoInfo.data.ip }} </div>
    <div id="list">
      <ol>
        <li v-for="info in GeoInfo.data" :key="info">
          {{info}}
        </li>
      </ol>
    </div>
  </div>
  <pre>{{ JSON.stringify(GeoInfo, null, '\t') }}</pre>
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
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
