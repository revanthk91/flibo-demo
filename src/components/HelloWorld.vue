<template>
  <div>
    <h1>Enter Number</h1>
    <p>Only integers in below</p>
    <input v-model='input_number' type='text' />
    <br/>
    <button v-on:click='input_handle'>Get Cubed </button>
    <h2 v:if="answer !== null">The Cube of the Number is {{answer}}</h2>
  </div>
</template>

<script>
  export default {
    name: 'HelloWorld',
    props: {
      msg: String
    },
    data() {
      return {
        input_number : null,
        answer: null
      }
    },
    methods: {
      input_handle: function() {
        let n = Number(this.input_number)
        if (!isNaN(n) && n!==0) {
          this.answer = n*n*n
        }
        else {
          alert("Please enter Integers Only.")
        }
        this.input_number = null
      }
    }

    //posibly Life Cycles
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
   * {
    text-align: center;
   }

   p {
    color: grey;
   }

   h1 {
    font-weight: bold;
   }

   input {
    padding: 1em;
    font-size: 2em;
    border: 4px solid grey;
   }

   button {
    margin: 1em;
    padding: 1em;
    font-size: 2em;
    border: 2px solid skyblue;
    border-radius: 60px;
   }
</style>
