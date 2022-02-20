<template>
  <div id="nav">
    <router-link to="/">Home</router-link> 
    <span class="separetor-line">|</span>
    <router-link :to="{name: 'Jobs' }">Jobs</router-link>
    <span class="separetor-line">|</span>
    <router-link :to="{name: 'About' }">About</router-link>
  </div>

  <button @click="back">
    <i class="fas fa-angle-left"></i> &nbsp; Go Back
    </button>
  <button @click="redirect">
    <i class="fas fa-home"></i> &nbsp; Redirect 
  </button>
  <button @click="forward">
    Go Forward &nbsp; <i class="fas fa-angle-right"></i>
    </button>

  <router-view/>

</template>

<script>
  export default {
    methods: {
      redirect() {
        this.$router.push({name: 'Home'})
      },
      back() {
        this.$router.go(-1)
      },  
      forward() {
        this.$router.go(1)
      }
    }
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

#nav {
  padding: 30px;
}

#nav a {
  font-size: 24px;
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
  padding: 10px;
  border-radius: 4px;
}

#nav a.router-link-exact-active {
  color: white;
  background: crimson;
}
button {
  margin: 0 10px;
  padding: 10px;
  border: none;
  border-radius: 4px;
}
.go-arrow {
  font-size: 20px;
  color: black;
}
.separetor-line {
  margin: 0 20px;
  font-size: 24px;
  color: #ccc;
}
.page-title {
  margin: 40px 0;
}
.loading {
  font-style: italic;
  margin: 50px auto;
}
</style>