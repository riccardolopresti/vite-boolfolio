<script>
import {store} from '../data/store.js'

export default {
  name: 'ProjectCard',
  data(){
    return{
      store
    }
  },
}
</script>

<template>
  <div class="container">
    <h1 class="text-center">HOME PAGE</h1>
    <div class="row">
      <div class="col d-flex flex-wrap ">
        <div v-for="project in store.projects" :key="project.id" class="card m-2" style="width: 18rem;">

          <div class="card-body">
            <h5 class="card-title">{{project.name}}</h5>
            <h6>{{project.client_name}}</h6>
            <p class="card-text">{{project.summary}}</p>
              
          </div>

        </div>
      </div>
    </div>
    
  </div>
</template>

<style lang="scss">
@use './src/styles/general'

</style>