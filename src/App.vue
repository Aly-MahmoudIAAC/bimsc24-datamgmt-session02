
<!-- // JAVASCRIPT -->
<script setup>

import { ref } from "vue";


// Task 1 Define variables and constants
let starter = ref("Data MGMT Assignment 02")

// Task 2 Define ref variables for input and display
const inputText = ref("");
const displayText = ref("");
// ref variables for color selection 
const selector = ref("")
const color = ref("")
const dynamicColor = ref("")

// Function to add text to the ref variable and display it
const addText = () => {
  displayText.value += inputText.value;
};

//Task 3 function for coloring 
const updateColor = () => {
  const element = document.querySelector(selector.value);
  if (element) {
    element.style.backgroundColor = color.value; 
    dynamicColor.value = color.value;
  }
}

</script>


<!-- the template is where the html code goes -->
<template>
  <div id="navbar" class="container">
      <p>{{ starter }}</p>
      <div id="title">Aly's website</div>
      <div id="top-bar">

      <img class="logo-image" alt="Iaac logo" src="./assets/iaac-white.png" />       
  
      </div>
  </div>

  <div id="flex">

  <div  id="sidebar" class="container"> DATA  
  <br><input v-model="inputText" placeholder="Enter text" />
      <button @click="addText">Add Text</button>
      
    <br>
    <input v-model="selector" type="text" placeholder="Enter selector"/>
    <input v-model="color" type="text" placeholder="Enter color">
  <button @click="updateColor" class="container" >change color</button>
  </div>

  <div id="main" class="container">  <p :style="{color: dynamicColor}">Main content</p> <p>{{ displayText }}</p>    </div>
  
  </div>
</template>



<!-- style is where the css code goes -->
<style scoped>
html{
    
  background-color: rgb(59, 59, 59); 
  color: rgb(255, 255, 255);
}

body{

  margin:0;
}

div{

  /* put the borders in the inside of container */
  box-sizing: border-box;
}



#navbar{

  height: 50px;
  display: flex;
  align-items: center;
  border-color: rgb(0, 0, 0);

  
}

#flex{
  
  display: flex;
  height: calc(100vh - 50px);
}

#sidebar{
  
  width:20%;
  border-color: rgb(179, 179, 179);

}

#main{
  width:80%;
  background-color: #f0f0f0;
  color: black;

}

#title{
  width: 80%;
  float: left;
  display: flex;
  justify-content: center;
}

.container{

  border-style: solid;
  border-width: 1px;

}
</style>
