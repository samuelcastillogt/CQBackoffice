<script setup lang="ts">
import Header from './components/Header.vue'
import Slidebar from "./components/Sidebar.vue"
</script>

<template>
  <div class="container">
  <Slidebar />
  <div class="otherside">
    <h1>Hola</h1>
    </div>
  </div>

</template>

<style scoped>
  .container{
    display: flex;
    flex-direction: row;
  }
  .otherside{
    background-color: #f8fafc;
    width: 100%;
    overflow-y: scroll;

  }
</style>
