<template>
<div class="home">

  <div class="header-bg">
    <h1 class="header">Planner</h1>
    <p class="sub-header">every day we change lifePlanner</p>
  </div>

  <div v-if="projects.length">
    <div v-for="project in projects" :key="project.id">
       <single-project :project="project"></single-project>
    </div>
  </div>

</div>
</template>

<script>
import SingleProject from '../components/SingleProject.vue'

export default {
  name: 'Home',
  components: {
     SingleProject
  },
  data(){
    return{
      projects: []
    }
  },

  mounted(){
    fetch('http://localhost:3000/projects')
    .then(res => res.json())
    .then(data => this.projects = data).catch(err => console.log(err.message))

  }
}
</script>
<style>
body{
  margin: 0px;
  padding: 0px;
  background-color: beige;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.header-bg{

  height: 400px;
  background-image: linear-gradient(to right,rgb(202, 244, 255, 0.4), rgb(96, 137, 252, 0.7)),
  url(../../public/photos/header-last.jpg);
  background-size: cover;
  clip-path: polygon(0 0, 100% 0, 100% 100%, 10% 89%);



}





</style>