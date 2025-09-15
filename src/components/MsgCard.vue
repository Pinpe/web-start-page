<template>
  <div id="msg_card" class="tilts">
    <span id="time">{{ time }}</span><br>
    <span id="date">{{ date }}</span>
    <span id="week">{{ week }}</span>
  </div>
</template>

<script setup>
  import { ref } from 'vue';
  import VanillaTilt from 'vanilla-tilt';

  VanillaTilt.init(document.querySelectorAll(".tilts"));

  // 定义响应式变量
  const time = ref('');
  const date = ref('');
  const week = ref('');

  // 星期几的中文映射
  const weeks = ['周日', '周一', '周二', '周三', '周四', '周五', '周六'];

  // 更新时间日期的函数
  const now = new Date();
  
  // 格式化时间 (HH:MM:SS)
  const hours = String(now.getHours()).padStart(2, '0');
  const minutes = String(now.getMinutes()).padStart(2, '0');
  time.value = `${hours}:${minutes}`;
  
  // 格式化日期 (YYYY-MM-DD)
  const year = now.getFullYear();
  const month = String(now.getMonth() + 1).padStart(2, '0'); // 月份从0开始
  const day = String(now.getDate()).padStart(2, '0');
  date.value = `${year}-${month}-${day}`;
  
  // 获取星期几
  week.value = weeks[now.getDay()];
</script>

<style scoped>
  @media screen and (max-width: 1420px) {
      #msg_card{
        float: none !important;
      }
    }
  #msg_card{
    width: 300px;
    height: 100px;
    text-align: center;
    float: left;
  }
  #time{
    font-size: 42px;
  }
  #date{
    margin-right: 8px;
  }
</style>