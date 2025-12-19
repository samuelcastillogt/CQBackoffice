<script setup lang="ts">
import Slidebar from "./components/Sidebar.vue"
import Editor from "./components/Editor.vue"
</script>

<template>
  <div class="container">
  <Slidebar />
  <div class="otherside">
    <Editor />
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
