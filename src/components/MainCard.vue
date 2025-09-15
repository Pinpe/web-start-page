<template>
  <div id="main_card" class="tilts">
    <LinkBtu name="博客" link="https://pinpe.top"></LinkBtu>
    <LinkBtu name="哔哩哔哩" link="https://www.bilibili.com/"></LinkBtu>
    <LinkBtu name="知乎" link="https://www.zhihu.com/"></LinkBtu>
    <LinkBtu name="DeepSeek" link="https://chat.deepseek.com/"></LinkBtu>
    <LinkBtu name="豆包" link="https://www.doubao.com/chat/"></LinkBtu>
  </div>
</template>

<script setup>
  import VanillaTilt from 'vanilla-tilt';
  import LinkBtu from './LinkBtu.vue';

  VanillaTilt.init(document.querySelectorAll(".tilts"));
</script>

<style scoped>
  #main_card{
    width: 300px;
    height: 310px;
    float:right;
  }
</style>