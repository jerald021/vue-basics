<template>
  <div Posts id="app">
    <NavBar/>

    <nav>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </nav>
    <router-view/>

    <p>basic op: {{2+2}}</p>
    <p>{{printString()}}</p>

    <div>
      <button @click="isTrue = !isTrue">Log In</button>
     <button v-if="!isTrue">Log Out</button> 
    </div>

    <br>
    <div>
      <button @click="changeColor" v-bind:style="{color: activeColor }">change color</button>
    </div>

    <Posts/>

    <Footer/>
  </div>
</template>

<script>
import NavBar from './components/NavBar.vue'
import Footer from './components/Footer.vue'
import Posts from './components/Posts.vue'

export default {
  data(){
    return{
       isTrue: true,
       activeColor: 'red',
    }
  },
  components:{
    NavBar,
    Footer,
    Posts,
  },
  methods:{
     printString(){
      const string1 = 'esto es una string';
      return string1;
    },
    changeColor(){
      this.activeColor = 'green';
    }
  },
  mounted(){
    // this.printString();   
  },
}


</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}

.dark-background{
  background-color: black;
}
.white-background{
  background-color: white;
}
</style>
