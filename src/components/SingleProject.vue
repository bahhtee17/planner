<template>
 <div class="container" @click="openIt">
     <div class="title">
        <h3>{{project.title}}</h3>
     </div>

     <div v-if="isOpen" class="details">
        <p>{{project.details}}</p>
     </div>
 </div>
</template>

<script>
export default {
    props: ['project'],

    data(){
        return{
            isOpen: false
        }
    },

    methods: {
        openIt(){
            this.isOpen = !this.isOpen
        }
    }

}
</script>

<style>
  .container{
      display: inline-block;
      width: 50vh;
      padding: 5px;
       margin-bottom: 10px;
      background-color: rgb(240, 240, 65);
      margin-left: 40%;
      color: #444;
      clip-path: polygon(0 0, 100% 0, 100% 100%, 0 77%);
  }

  .title{
      margin-left: 50px;
  }

  .details{
      margin-left: 55px;
  }
</style>