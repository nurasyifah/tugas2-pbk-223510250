<template>
  <h1>Tugas 2 @nurasyifah_</h1><br><br><!-- membuat beberapa elemen HTML yang berbeda-->
  <br><h2>Type the text below :</h2><br><br>
  <p style="text-align: justify;">hello I'm cipa, my family calls me that I'm the 3rd child of 3 siblings 
    yes I'm the last child but I'm not spoiled ok :) I'm was born on May 11, 2004 yes now I'm 19 years old 
    my zodiac sign is Taurus (the stubborn bull) but it's okay then my hobby is reading anything because I like 
    learning then my favorite food is chocolate "Dairy Milk" my favorite drink is "Taro". The last is my quote that 
    always remember is "if you never do, you'll never know" and "learning is a process to become better than before".
  </p><br><br>
  <div class="container">
    <input type="text" v-model="text" @input="updateText" @keydown="handleKeyDown"
    class="custom-input" :class="{ 'input-highlight': isHighlighted }" placeholder="type here"> <!-- penggunaan elemen input teks--> <!-- penggunaan class bindings dalam elemen-->
    <p style="text-align: justify;" :style="{ color: textColor, fontSize: '20px', 
    marginTop: '10px' }">input text: {{ text }}</p><br> <!-- penggunaan style bindings dalam elemen-->
    <button @click="handleButtonClick" class="enter-button">Enter</button> <!-- penggunaan event listeners dengan merubah warna teks yang di inputkan jika menekan botton enter-->
  </div>
</template>

<script setup>
import { ref } from 'vue'

const text = ref('')
const textColor = ref('black')
const isHighlighted = ref(false)

function updateText(event) {
  text.value = event.target.value;
}

function handleKeyDown(event) {
  if (event.key === 'Enter') {
    textColor.value = 'skyblue';
    isHighlighted.value = true;
  } else {
    textColor.value = 'black';
    isHighlighted.value = false;
  }
}

function handleButtonClick() {
  textColor.value = 'skyblue';
  isHighlighted.value = true;
}
</script>

<style>
body {
  background-color: skyblue;
}

body, h1, h2, p, input, button {
  font-family: 'Times New Roman', Times, serif;
  font-weight: bold;
}

.container {
  max-width: 600px;
  margin: 50px auto;
  padding: 20px;
  border-radius: 8px;
  background-color: #fff;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
}

.custom-input {
  width: 100%;
  padding: 8px 16px;
  font-size: 14px;
  border-radius: 4px;
  text-align: center; 
  margin-bottom: 15px;
}

.enter-button {
  display: block;
  margin: 0 auto;
  padding: 8px 16px;
  font-size: 14px;
  background-color: black;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.enter-button:hover {
  background-color: skyblue;
}
</style>
