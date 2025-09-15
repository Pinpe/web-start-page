<template>
  <TitleText></TitleText>
  <MainCard class="card_g"></MainCard>
  <MsgCard class="card_g"></MsgCard>
  <BingCard class="card_g"></BingCard>
  <HitokotoCard class="card_g"></HitokotoCard>
</template>

<script setup>
import { onMounted } from 'vue'
import Cursor from './thirdparty/cursor.js'
import MsgCard from './components/MsgCard.vue';
import HitokotoCard from './components/HitokotoCard.vue';
import TitleText from './components/TitleText.vue';
import BingCard from './components/BingCard.vue';
import MainCard from './components/MainCard.vue';

onMounted(() => {
  new Cursor()
})
</script>

<style>
  * {
    cursor: url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 8 8' width='8px' height='8px'><circle cx='4' cy='4' r='4' fill='black' opacity='.45'/></svg>") 4 4, auto !important;
  }
  body{
    background-color: #e7f1f0;
    padding-left: 23%;
    padding-right: 23%;
    padding-top: 5%;
    font-family: Blueaka,sans-serif;
    color: #000000bf;
  }
  .card_g{
    background-color: #fff;
    border-radius: 16px;
    padding-left: 35px;
    padding-top: 25px;
    padding-right: 35px;
    padding-bottom: 20px;
    box-shadow: 0 20px 25px -5px rgb(0 0 0 / .1), 0 8px 10px -6px rgb(0 0 0 / .1);
    margin-top: 25px;
  }
  #cursor {
      position: fixed;
      width: 16px;
      height: 16px;
      background: #000;
      border-radius: 8px;
      opacity: 0.25;
      z-index: 10086;
      pointer-events: none;
      transition: 0.2s ease-in-out;
      transition-property: background, opacity, transform;
  }

  #cursor.hidden {
      opacity: 0;
  }

  #cursor.hover {
      opacity: 0.1;
      transform: scale(2.5);
  }

  #cursor.active {
      opacity: 0.5;
      transform: scale(0.5);
  }
</style>
