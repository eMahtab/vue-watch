<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <button v-on:click="updateMsg">Update</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  methods: {
    updateMsg(){
      // This will result in watch function on msg property being called on each click on update button
      // since the value of msg property is actually being updated on each click, because of changing Date value 
      
      // this.msg = "New message generated on "+new Date()

      this.msg = "New message generated on "

      // This will result in watch function on msg property beign called only once
      // since the value of msg property actually only changes on first click of update button
      // on later clicks of update button, we are assigning the same value to msg property
      // which means the value of msg property didn't change from its previous value, so watch function is not called 
      

    }
  },
  watch: {
    msg : function(value){
      alert("Message Updated ::: "+this.msg)
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
