<template>
  <div id="hitokoto_card" class="tilts">
    <a href="#" id="hitokoto_text">...</a>
  </div>
</template>

<script setup>
  import { onMounted } from 'vue';
  import VanillaTilt from 'vanilla-tilt';

  onMounted(() => {
    VanillaTilt.init(document.querySelectorAll("#hitokoto_card.tilts"));
    fetch('https://v1.hitokoto.cn')
      .then(response => response.json())
      .then(data => {
        const hitokoto = document.querySelector('#hitokoto_text')
        hitokoto.href = `https://hitokoto.cn/?uuid=${data.uuid}`
        hitokoto.innerText = data.hitokoto
      })
      .catch(console.error)
  });
</script>

<style scoped>
  @media screen and (max-width: 1420px) {
    #hitokoto_card{
      float: none !important;
    }
  }
  #hitokoto_card{
    width: 300px;
    text-align: center;
    float: left;
  }
  #hitokoto_text{
    color: #000000bf;
    text-decoration:none;
  }
</style>