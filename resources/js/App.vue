<template>
  <div>
    <ul>
        <li v-for="post in posts" :key="post.id">
          <div> {{post.title}}</div>
            <div> {{post.content}}</div>
        </li>

    </ul>

  </div>






</template>

<script>
export default {
    name : 'App',
    data(){
        return{
            apiUrl:'/api/posts',
            posts : null
        }
    },

    methods:{
         getApi(){
            axios.get(this.apiUrl)
            .then(res=>{
             console.log(res.data);
             this.posts=res.data.posts;
            //  console.log(this.posts);

            })

         },

    },
     mounted(){
         this.getApi()

    },
}
</script>

<style>

</style>
