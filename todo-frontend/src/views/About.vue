<template>
  <div class="about">
    <h1>This is an about page</h1>
  <div v-for="item in items" v-bind:key="item.id">
    {{item}}
  </div>
  </div>
</template>

<script>
// @ is an alias to /src
const axios = require('axios');

export default {
  name: "about",
  data(){
    return{
      items: [],
    }
  },
  mounted: function () {
    axios.get('http://localhost:8080/to-do/todo-backend/itemi.json').then(response=>{
      this.items = response.data;
    }).catch (error => {console.log(error)});
  }
};
</script>
