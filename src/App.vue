<script>
import ProjectCard from '../src/components/ProjectCard.vue'

import axios from 'axios'
import {store} from '../src/data/store.js'

export default {
  name: 'App',
  components:{
    ProjectCard
  },
  data(){
    return{
      store,
      baseUrl:'http://127.0.0.1:8000/api/projects'
    }
  },
  methods:{
    getApi(){
      axios.get(this.baseUrl)
        .then(result => {
          store.projects = result.data.projects;
          console.log(store.projects)
        })
    }
  },
  mounted(){
    this.getApi(this.baseUrl)
  }
}
</script>

<template>
  <ProjectCard />
</template>

<style lang="scss">
@use './src/styles/general'

</style>