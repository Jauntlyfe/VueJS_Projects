<template>
  <div class="about">
    <h1> This is the about page</h1>
      <p> This is just simple information </p>
        {{greeting}}
    <input v-model="greeting">

    <br>

    <div v-if="count === 1">
      This information is displayed
    </div>

    <br>

    <div v-show="count === 1">
      Green
    </div>

  </div>
</template>

<script>
  export default {
    name: 'about',
    data () {
      return{
        greeting: "This is a greeting being passed on the about page",
        count: 1
      }

    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1, h2 {
    font-weight: normal;
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
  li {
    display: inline-block;
    margin: 0 10px;
  }
  a {
    color: #42b983;
  }
</style>
