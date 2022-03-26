<template>
  <div>
      <ul>
          <li v-for="(post ,index) in posts" :key="index">
              {{post.title}}
          </li>
      </ul>
  </div>
</template>

<script>
export default {
    name:'Main',
    data(){
        return{
            posts:[]
        };
    },
    created(){
        axios.get('/api/posts')
    .then((response)=> {
        // handle success
        this.posts = response.data;
    })

    }
}
</script>

<style>

</style>