<script setup>
import TODO_list from "./components/TODO_list.vue"
</script>

<template>
  <header>TODO List</header>
  <div>
    <TODO_list/>
  </div>
</template>

<style>
  body{
    background-color: black;
    margin: 0;
    color: white;
  }
  header{
    width: 95%;
    height: 30px;
    background-color: rgb(53, 52, 52);
    border: 1px solid rgb(180, 179, 179);
    border-radius: 5px;
    text-align: center;
    color: white;
    font-weight: bolder;
    font-size: 30px;
    padding: 10px 5px;
    margin: 25px;
  }
  
</style>
