<template>
  <button @click="href(props.link)">{{ props.name }}</button>
</template>

<script setup>
  import { defineProps } from 'vue';

  const props = defineProps(['link', 'name'])

  function href(link){
    location.href = link;
  }
</script>

<style scoped>
  button{
    border: none;
    font-size: 15px;
    padding: 10px 10px 10px 10px;
    background-color: #dcf4f4;
    border-radius: 6px;
    margin-top: 5px;
    color: #00b8b9;
    transition:ease-in-out .2s;
    width:100%;
  }
  button:hover{
    background-color: #00b8b9;
    color: #fff;
  }
</style>