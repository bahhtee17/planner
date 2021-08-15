<template>
 <div class="container">
     <div class="title">
        <h3>{{project.title}}</h3>
     </div>

     <div class="details">
        <p>{{project.details}}</p>
     </div>
 </div>
</template>

<script>
export default {
    props: ['project']

}
</script>

<style>

</style>