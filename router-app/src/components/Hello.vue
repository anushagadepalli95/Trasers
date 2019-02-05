<template>
  <div class="hello">
    
 <h2>My deepest, darkest question: {{name}}</h2>
<input v-model="name"/>

  </div>

</template>

<script>
import Vuetable from 'vuetable-2';
import axios from "axios";
export default {
 name: 'Child',
  // To use props, they must be declared
  props: {
    parentData: Object,
    stringProp: String,
    title: String
  },
 data(){
    return {
      name:'Lucas',
      ip: ''
    }

  },
  mounted() {
    
            axios({ method: "GET", "url": "https://vuetable.ratiw.net/api/users" }).then(result => {
                this.ip = result.data.data;
                console.log(this.ip);

            }, error => {
                console.error(error);
            });
        }
 }

  

</script>