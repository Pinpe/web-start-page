<template>
  <div :style="{ '--main-color': props.mainColor }">
    <span id="title1">欢迎</span>
    <span id="title2">回到互联网，您想从哪里开始？</span>
  </div>
</template>

<script setup>
  import { defineProps } from 'vue';

  const props = defineProps(['mainColor'])


</script>

<style scoped>
  @media screen and (max-width: 1420px) {
    #title1{
      display: none !important;
    }
    #title2{
      display: none !important;
    }
  }
  #title1{
    color: var(--main-color);
    font-size: 50px;
  }
  #title2{
    color: v-bind("mainColor + '50'");
    font-size: 35px;
  }
</style>