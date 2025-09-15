<template>
    <div id="bing_card" class="tilts">
      <input type="text" v-model="key_con" id="key">
      <button id="scr" @click="scr(key_con)">必应一下</button>
    </div>
</template>

<script setup>
  import { onMounted } from 'vue';
  import VanillaTilt from 'vanilla-tilt';
  onMounted(() => {
    VanillaTilt.init(document.querySelectorAll(".tilts"));
  })

  function scr(key_con){
    location.href = "https://www.bing.com/search?q=" + key_con;
  }
</script>

<style scoped>
  #bing_card{
    width: 300px;
    text-align: center;
    float: left;
  }
  #scr{
    border: none;
    font-size: 15px;
    padding: 5px 10px 5px 10px;
    background-color: #dcf4f4;
    border-radius: 6px;
    margin-left: 5px;
    color: #00b8b9;
    transition:ease-in-out .2s;
  }
  #scr:hover{
    background-color: #00b8b9;
    color: #fff;
  }
  #key{
    border: none;
    font-size: 15px;
    padding: 7px 10px 7px 10px;
    border-radius: 6px;
    background-color: #dcf4f4;
    outline-color: #00b8b9;
    color: #00b8b9;
    width: 195px;
  }
</style>