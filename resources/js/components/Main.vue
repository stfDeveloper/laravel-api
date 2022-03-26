<template>
  <div>
      <ul>
          <li v-for="(post ,index) in posts" :key="index">
              {{post.title}} <br>
              {{post.content}} <br>
              <span v-if="post.category != null">categories: {{post.category.type}}</span>
              <span v-for="(tag, index) in post.tags" :key="index">tags:{{tag.name}} </span>
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