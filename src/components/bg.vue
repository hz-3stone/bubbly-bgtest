<script setup>
import { onMounted } from 'vue';

onMounted(async () => {
  await import('bubbly-bg');
  bubbly({
    blur: 0, //ぼかし
    colorStart: '#f0f8ff', //背景グラデーション始まりの色
    colorStop: '#f0f8ff', //背景グラデーション終わりの色
    radiusFunc:() => 2 + Math.random() * 10, //大きさ
    // angleFunc:() => -Math.PI / 2, //向き
    velocityFunc:() => Math.random() * 0.05, //速さ
    bubbleFunc:() => `hsla(${200 + Math.random() * 50}, 100%, 65%, .1)`, //色彩(hsla)
    bubbles:10, //個数
    compose: 'source-over', //色ブレンド
    canvas: background //キャンバスID指定
  });
});

</script>

<template>
  <canvas id="background" style=""></canvas>
</template>

<style scoped>
  #background {
    position:fixed;
    z-index:-1;
    left:0;
    top:0;
    min-width:100vw;
    min-height:100vh;
  }
</style>
