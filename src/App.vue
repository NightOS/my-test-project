<template>
  <div>
    <v-header :seller="seller"></v-header>
    <div>
      <router-link to="/goods">商品</router-link>
      <router-link to="/ratings">评论</router-link>
      <router-link to="/seller">商家</router-link>
    </div>
    <router-view :seller="seller"/>
  </div>
</template>

<script >

import axios from 'axios'
import header from "./components/header/header.vue"

const ERR_OK = 0;

export default {
  data(){
    return {
      seller:{
        type:Object
      }
    }
  },
  created(){
    axios.get("../static/data.json").then((response)=>{
      let data = response.data;
      if(data.errno === ERR_OK){
        this.seller = data.data;
      }
    }).catch((error)=>{
      console.log(error);
    })
  },
  components: {
    "v-header":header
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
