<script>
import axios from 'axios'

export default {
  name: 'App',
  data(){
    return{
      baseUrl:'http://127.0.0.1:8000/api/projects',
      projects:[]
    }
  },
  methods:{
    getApi(){
      axios.get(this.baseUrl)
        .then(result => {
          this.projects = result.data.projects;
          console.log(this.projects)
        })
    }
  },
  mounted(){
    this.getApi(this.baseUrl)
  }
}
</script>

<template>
  <h1>ciao</h1>
</template>


<style>

</style>