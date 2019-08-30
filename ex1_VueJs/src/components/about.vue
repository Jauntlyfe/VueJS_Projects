<template>
  <div class="about">
    <h1> This is the about page</h1>
    <p> This is just simple information </p>
    <p>{{greeting}} </p>
    <p> {{textBox}}</p>

    <input v-model="textBox">

    <br>

    <div v-if="count === 1">
      This information is displayed
    </div>

    <div v-show="count === 1">
      Green
    </div>

<!--   Email: <input v-model="email" :class="{red: email.length < 2}">-->
       Email: <input v-model="email" :class="[email.length < 2 ? 'red' : 'green' ]">
    <br>

    <button onclick="alert('Hi')" v-bind:disabled="email.length < 2">
      Submit
    </button>

    </div>
</template>

<script>
  export default {
    name: 'about',
    data () {
      return{
        greeting: "This is a greeting being passed on the about page",
        count: 1,
        textBox: " ",
        email: " "
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
  .red{
    border: 2px solid red;
  }
  .green{
    border: 2px solid green;
    font-size: 20px;
  }
</style>
