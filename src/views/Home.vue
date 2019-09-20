<template>
  <div class="home">
      <div class="container">
          <div class="header">
            <p>{{ somedata.situationId }}</p>
          </div>
    </div>
  </div>
</template>

<script>
import { Component, Vue } from 'vue-property-decorator';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src
import axios from 'axios';
import VueAxios from 'vue-axios';

export default {

data(){
  return{
    somedata: ''
  };
},
created() {
  this.getResult();
},
methods: {
  getResult: function() {
    Vue.axios.get('http://localhost:62940/api/Questions').then((response) => {
      console.log(response.data);
      this.somedata = response.data;
    })
  }
}


}
</script>

<style>
.header{
  font-size: 32px;
}
</style>
