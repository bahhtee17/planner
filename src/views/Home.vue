<template>
<div class="home">

  <div class="header-bg">
    <h1 class="header">Planner</h1>
    <p class="sub-header">every day we change life</p>
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

  height: 50vh;
  background-position: top;
  background-image: linear-gradient(to right,rgba(218, 255, 11, 0.4), rgba(255, 251, 5, 0.74)),
  url(../../public/photos/header-last.jpg);
  background-size: cover;
  clip-path: polygon(0 0, 100% 0, 100% 100%, 10% 89%);
  color: #fff;
  text-transform: uppercase;
  left: 50%;
  top: 50%;

}

.header{
font-size: 60px;
font-weight: 400;
letter-spacing: 35px;
transform: translate(38%, 50%);
}

.sub-header{
  display: block;
  font-size: 15px;
  font-weight: 400;
  letter-spacing: 7.5px;
  transform: translate(41%, 50%);
}

</style>