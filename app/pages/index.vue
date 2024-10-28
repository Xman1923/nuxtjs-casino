<script setup lang="ts">
const runtimeConfig = useRuntimeConfig();
const colors = ['#ff4757', '#ffa502', '#70a1ff', '#1e90ff', '#2ed573', '#ff6348', '#ff6b81']; // Casino temalı renkler
const color = useState('color', () => colors[Math.floor(Math.random() * colors.length)]);
</script>

<template>
  <div class="casino-centered">
    <h1 :style="{ color }">
      {{ runtimeConfig.public.welcomeText }}
    </h1>
    <p>Hoş geldiniz! En popüler oyunlarımızı keşfedin:</p>
    <ul>
      <li><NuxtLink to="/slots">Slot Makineleri</NuxtLink></li>
      <li><NuxtLink to="/blackjack">Blackjack</NuxtLink></li>
      <li><NuxtLink to="/roulette">Rulet</NuxtLink></li>
      <li><NuxtLink to="/poker">Poker</NuxtLink></li>
    </ul>
    <NuxtLink to="/" external>
      Yenile
    </NuxtLink>
  </div>
</template>

<style scoped>
.casino-centered {
  position: absolute;
  width: 100%;
  text-align: center;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  margin: 0;
  font-family: 'Arial', sans-serif; /* Daha modern bir font */
  background: linear-gradient(135deg, #74ebd5, #acb6e5); /* Arka plan için bir gradient */
}
h1 {
  font-size: 32px;
  text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.3); /* Metne gölge efekti */
}
ul {
  list-style-type: none; /* Liste işaretlerini kaldır */
  padding: 0;
}
li {
  margin: 10px 0;
}
a {
  color: #1e90ff; /* Link rengi */
  text-decoration: none;
  font-size: 18px;
}
a:hover {
  text-decoration: underline;
}
</style>