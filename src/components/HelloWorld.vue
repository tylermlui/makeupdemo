<template>
  <div class="hello">
    <div class="search">
      <h2>{{ msg }}</h2> 
      <input type="text" placeholder="Search">
      <a href="https://www.google.com/" target ="_blank">Login/Register </a>
    </div>
    <br>
    <div class="match">
      Find your match
    </div>
    <br>
    <hr>
    <button @click="submitEyes" class="button">Eye Products</button>
    <button @click="submitLips" class="button">Lip Products</button>
    <button @click="submitFace" class="button">Face Products</button>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  // Your component options
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      inputData: '' ,// Data property to store input field value
      responseData :[]
    };
  },
  methods: {
    submitLips() {
      const data_list = ["lipstick","lipliner"]
      axios.post('http://localhost:8000/submit_data_view/', {
        data: data_list
      })
      .then(response => {
        console.log('Response:', response.data);
        // Handle response if needed
      })
      .catch(error => {
        console.error('Error:', error);
        // Handle error if needed
      });
    },
    submitFace(){
        const data_list = ["bronzer","blush","foundation"]
        axios.post('http://localhost:8000/submit_data_view/', {
        data: data_list
      })
      .then(response => {
        console.log('Response:', response.data);
        // Handle response if needed
      })
      .catch(error => {
        console.error('Error:', error);
        // Handle error if needed
      })
    },
    submitEyes(){
        const data_list = ["eyeliner","eyebrow","eyeshadow"]
        axios.post('http://localhost:8000/submit_data_view/', {
        data: data_list
      })
      .then(response => {
        console.log('Response:', response.data);
        // Handle response if needed
      })
      .catch(error => {
        console.error('Error:', error);
        // Handle error if needed
      })
    }
  }
}
</script>

<style scoped>
.hello {
  margin-left: 2%;
  margin-right: 2%;
}

h3 {
  margin: 40px 0 0;
}
.button {
  background-color: white;
  border: solid black 1px;
  color: black;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
  border-radius: 12px;
  transition: background-color 0.3s;
}

.search {
  display: flex;
  align-items: center; /* Align items vertically */
}

.search h2 {
  margin-right: 10%; /* Adjust the margin between h1 and input */
}

.match {
  display: flex;
  justify-content: center;
}

input[type="text"] {
  display: flex;
  justify-content: center;
  flex-grow: 1; /* Make the input element grow to fill remaining space */
  outline: none;
  border: 1px solid rgb(70, 69, 69);
  background-color: rgb(242, 240, 240);
  padding: 5px 8px; /* Adjust padding */
  border-radius: 15px; /* Make the input rounded */
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

.search a {
  color: black;
  margin-right: 5%;
  margin-left: 10%;
  text-decoration: none;
}

a {
  color: #000000;
}

</style>
