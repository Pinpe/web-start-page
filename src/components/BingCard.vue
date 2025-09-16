<template>
    <div id="bing_card" class="tilts" :style="{ '--main-color': props.mainColor }">
      <input type="text" v-model="key_con" id="key">
      <button id="scr" @click="scr(key_con)">必应一下</button>
    </div>
</template>

<script setup>
  import { onMounted, defineProps } from 'vue';
  import VanillaTilt from 'vanilla-tilt';

  const props = defineProps(['mainColor'])

  onMounted(() => {
    VanillaTilt.init(document.querySelectorAll(".tilts"), {reverse:true});
  })

  function scr(key_con){
    location.href = "https://www.bing.com/search?q=" + key_con;
  }
</script>

<style scoped>
  @media screen and (max-width: 1420px) {
    #bing_card{
      float: none !important;
    }
  }
  #bing_card{
    width: 300px;
    text-align: center;
    float: left;
  }
  #scr{
    border: none;
    font-size: 15px;
    padding: 5px 10px 5px 10px;
    background-color: v-bind("mainColor + '22'");
    border-radius: 6px;
    margin-left: 5px;
    color: var(--main-color);
    transition:ease-in-out .2s;
  }
  #scr:hover{
    background-color: var(--main-color);
    color: #fff;
  }
  #key{
    border: none;
    font-size: 15px;
    padding: 7px 10px 7px 10px;
    border-radius: 6px;
    background-color: v-bind("mainColor + '22'");
    outline-color: var(--main-color);
    color: var(--main-color);
    width: 195px;
  }
</style>