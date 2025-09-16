<template>
  <div id="main_card" class="tilts">
    <LinkBtu :name="props.link1.name" :link="props.link1.url" :mainColor="props.mainColor"></LinkBtu>
    <LinkBtu :name="props.link2.name" :link="props.link2.url" :mainColor="props.mainColor"></LinkBtu>
    <LinkBtu :name="props.link3.name" :link="props.link3.url" :mainColor="props.mainColor"></LinkBtu>
    <LinkBtu :name="props.link4.name" :link="props.link4.url" :mainColor="props.mainColor"></LinkBtu>
    <LinkBtu :name="props.link5.name" :link="props.link5.url" :mainColor="props.mainColor"></LinkBtu>
  </div>
</template>

<script setup>
  import VanillaTilt from 'vanilla-tilt';
  import LinkBtu from './LinkBtu.vue';
  import { defineProps } from 'vue';

  const props = defineProps(['mainColor', 'link1', 'link2', 'link3', 'link4', 'link5'])

  VanillaTilt.init(document.querySelectorAll(".tilts"), {reverse:true});
</script>

<style scoped>
  @media screen and (max-width: 1420px) {
    #main_card{
      float: none !important;
    }
  }
  #main_card{
    width: 300px;
    height: 310px;
    float:right;
  }
</style>