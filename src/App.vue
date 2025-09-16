<template>
  <TitleText :mainColor="config.mainColor"></TitleText>
  <MainCard 
    class="card_g" 
    :mainColor="config.mainColor"
    :link1="config.link1" 
    :link2="config.link2" 
    :link3="config.link3" 
    :link4="config.link4" 
    :link5="config.link5"
  ></MainCard>
  <MsgCard class="card_g"></MsgCard>
  <BingCard class="card_g" :mainColor="config.mainColor"></BingCard>
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

  // 配置
  const config = {
    mainColor: '#9e8eef',
    link1: {
      name: 'Pinpe的云端',
      url: 'https://pinpe.top'
    },
    link2: {
      name: '哔哩哔哩',
      url: 'https://www.bilibili.com/'
    },
    link3: {
      name: '知乎',
      url: 'https://www.zhihu.com/'
    },
    link4: {
      name: 'DeepSeek',
      url: 'https://chat.deepseek.com/',
    },
    link5: {
      name: '豆包',
      url: 'https://www.doubao.com/chat/'
    },
  }

  onMounted(() => {
    new Cursor()
  })
</script>

<style>
  @media screen and (max-width: 1420px) {
    body{
      padding-left: 1% !important;
      padding-right: 1% !important;
      padding-top: 1% !important;
    }
  }
  /* 这里也要修改，颜色+1c */
  :root{
    --main-color: #9e8eef1c
  }
  * {
    cursor: url("data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 8 8' width='8px' height='8px'><circle cx='4' cy='4' r='4' fill='black' opacity='.45'/></svg>") 4 4, auto !important;
  }
  body{
    padding-left: 23%;
    padding-right: 23%;
    padding-top: 5%;
    font-family: Blueaka,sans-serif;
    color: #000000bf;
    background-color: var(--main-color);
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
