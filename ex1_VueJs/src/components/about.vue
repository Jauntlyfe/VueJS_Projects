<template>
  <div class="about">
    <h1> Examples working in Vue Js </h1>
    <br>
    <br>
    <h1> Example #1 - Binding text to input box:</h1>
    <h2>When typing in the box you should see the text render on the page at the same time.</h2>
    <br>
    Type Here: <input v-model="textBox">

      <p>  <b> Text Entered: </b> {{textBox}}</p>

    <br>
    <br>
    <br>

    <h1> Example #2 - Using "v-if" to render content:</h1>
    <h2> In the data() object you can create a variable to set it to show HTML properties <br>
    based on a condition using <b>v-if</b></h2>
    <br>

    <div v-if="count === 1">
      <b>This information is displayed here because <b>count</b> === 1</b>

    </div>

    <br>


    <p> <b>"Green"</b> is not rendered here because count === 2</p>
    <div v-show="count === 2">
      "Green"
    </div>


    <br>
    <br>
    <br>

    <h1> Example #3 - Binding a model to an HTML element, Example : "button"</h1>
<!--   Email: <input v-model="email" :class="{red: email.length < 2}">-->
       Email: <input v-model="email" :class="[email.length < 2 ? 'red' : 'green' ]">
    <br>

    <button onclick="alert('Hi')" v-bind:disabled="email.length < 2">
      Submit
    </button>

    <br>
    <br>
    <br>
    <br>

    <h1> Example #4 - Looping </h1>
    <input v-model="newCat" v-on:keyup.enter="addKitty" class="add">
    <button  v-on:click="addKitty">
       + ADD
    </button>

<!--    <button v-on:click="catCount" > Kittify </button>-->
    <button v-on:click="addLastName" > Kittify </button>
    <ul class="listStyle">
      <li v-for="cat in cats" v-model="cats">
            <!-- Adding a filter -->
<!--        {{cat | capitalize | kittify}}-->
        {{cat | capitalize }}
      </li>
    </ul>

    </div>
</template>

<script>
  import JQuery from 'jquery'
  let $ = JQuery;

  export default {
    name: 'about',
    data() {
      return {
        greeting: "This is a greeting being passed on the about page",
        count: 1,
        textBox: " ",
        email: " ",
        cats: [
          'Bosco',
          'Butch',
          'Speedy',
          'Larry'
        ],

        smallCats: [
          {
            name: 'larry'
          },
          {
            name: 'ronald'
          }
          ],
        // The input box will be blank on page load
        newCat: ''
      }
    },
    methods: {
      addKitty: function () {

        //Validation to check for empty input box
        if(this.newCat === ''){
          alert("Please enter a name");
          $(".add").css("background-color", "red");
        } else{
          $(".add").css("background-color", "white");
        }

        //Pushes the new cat to the array
        this.cats.push(this.newCat);
        //The model is cleared when entered is pressed
        this.newCat = '';




      },
      catCount: function () {
        var i;
        for(i=0; i < this.cats.length; i++){}
        alert("The number of cats are" + i);
        //this.cats.join("Copeland");
      },
      addLastName: function () {

          var i = 0;
          for(i; this.cats.length < i; i++){

          }
          // i = the amout of objects

          this.cats.push("Copeland");
          if(this.cats[i] === "Copeland"){
            alert("Stp")
          }
          //alert(this.cats);
          var arr = [];
          //arr = arr.push(this.cats);
          this.cats.push(this.cats[1] + "Miudskds")



      }

    },
    filters: {
      capitalize: function(value) {
        return value.toUpperCase()
      },
      kittify: function(value) {
        return value + "y"
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
  .listStyle, li {
    list-style-type: square;
    display: block;
  }
</style>
