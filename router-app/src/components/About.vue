<template>
  <div id="login">
     <!-- <h1>Your IP is {{ ip }}</h1>  -->
      <div class="row">
            <Child title="This is my title"></Child>
             <Child :parentData="{name: 'Noelia O'}"></Child>
             <Child :parentData="myData"></Child>
                 <Child :stringProp="stringMessage"></Child>
        </div>

 
  </div>
</template>

<script>
import axios from "axios";
import Vuetable from 'vuetable-2'

import FieldsDef from "./../FieldsDef.js";
import Child from "./Hello.vue";

export default {
  name: 'About',
 

   components: {
    Vuetable   
  },

  data(){
    return {
      name:'Lucas'
    }

  },
 components: {
    Child
  },

  // mounted() {
    
            // axios({ method: "GET", "url": "https://vuetable.ratiw.net/api/users" }).then(result => {
            //     this.ip = result.data.data;
            //     console.log(this.ip);

            // }, error => {
            //     console.error(error);
            // });
        // },
        methods:{
          sendData() {
                axios({ method: "POST", "url": "https://httpbin.org/post", "data": this.input, "headers": { "content-type": "application/json" } }).then(result => {
                    this.response = result.data;
                    console.log(this.input);
                }, error => {
                    console.error(error);
                });
            }
        }
}
</script>
 