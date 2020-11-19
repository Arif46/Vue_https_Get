<template>
    <div class="container">
        this is blog
            <div v-for="(blog ,id) in blogs" :key="id">
                <h1>{{blog.Id}}</h1>
                    <h3>{{blog.userId}}</h3>
                    <h3>{{blog.title}}</h3>
                    <h5>{{blog.body}}</h5>
            </div>
    </div>
</template>
<script>
   export default {
       data(){
           return {
                blogs:[]
           }
       },
       created(){
           this.$http.get('https://jsonplaceholder.typicode.com/posts')
           .then((data)=>{
               console.log(data);
               this.blogs=data.body.slice(0,10)
           })
       }
   }
</script>
<style>
   div{
       color:red
   }
</style>