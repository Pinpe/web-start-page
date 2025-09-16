<template>
  <button @click="href(props.link)" :style="{ '--main-color': props.mainColor }">{{ props.name }}</button>
</template>

<script setup>
  import { defineProps } from 'vue';

  const props = defineProps(['mainColor' ,'link', 'name'])

  function href(link){
    location.href = link;
  }
</script>

<style scoped>
  button{
    border: none;
    font-size: 15px;
    padding: 10px 10px 10px 10px;
    background-color: v-bind("mainColor + '22'");
    border-radius: 6px;
    margin-top: 5px;
    color: var(--main-color);
    transition:ease-in-out .2s;
    width:100%;
  }
  button:hover{
    background-color: var(--main-color);
    color: #fff;
  }
</style>