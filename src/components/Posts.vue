<template>
<div>
    <h1>post template</h1>
  <!-- <p>{{printPosts()}}</p> -->
  <div class="post" v-for="post in Posts" :key="post.title">
      <h2>{{post.title}}</h2>
      <p>{{post.description}}</p>
      <p>{{post.content}}</p>
  </div>
</div>
  
</template>

<script>
export default {
    data(){
    return{
       isTrue: true,
       Posts: [
             {
                title: 'title1',
                description: 'desc1',
                content: 'content1',
             },
             {
                title: 'title2',
                description: 'desc2',
                content: 'content2',
             },
             {
                title: 'title3',
                description: 'desc3',
                content: 'content3',
             },
         ]
    }
  },
    methods:{
    //  printPosts(){
         
    // }
  },
  mounted(){
    //    this.printPosts();
  }
}
</script>


<style>
.post{
    border-color: gray;
    border: 5px;
    color: blue;
}

</style>