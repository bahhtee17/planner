<template>
 <div class="container" @click="openIt">
     <div class="title">
        <h3>{{project.title}}</h3>

        <div class="icons">
            <span class="material-icons">done</span>

            <span class="material-icons">edit</span>

            <span class="material-icons">delete</span>

        </div>
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

     margin: 20px auto;
     background: rgb(241, 255, 42);
     padding: 10px 20px;
     border-radius: 4px;
     box-shadow: 1px 2px 3px rgba(0, 0, 0, 0);
     height: 50%;
     border-left: 4px solid #000;
      clip-path: polygon(0 0, 100% 0, 100% 100%, 0 77%);
  }
  h3{
      cursor: pointer;
  }

.title{
    display: flex;
    justify-content: space-between;
    align-content: center;

}

.material-icons{
    margin-left: 5px;
    margin-block: 20px;
    cursor: pointer;
}

.material-icons:hover{
    color: #444
}
</style>