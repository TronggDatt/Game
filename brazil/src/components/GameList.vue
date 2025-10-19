<template>
  <div class="max-w-md mx-auto p-4">
    
    <!-- Banner -->
    <div class="bg-green-700 text-white rounded-lg p-4 mb-6 relative h-24 flex items-center justify-between overflow-hidden">

      <h1 class="font-bold text-lg z-10">BestGame.vip</h1>

      <div class="relative w-40 h-40 rounded-lg overflow-hidden">
        <transition-group name="slide" tag="div" class="flex">
          <img
            v-for="(banner, index) in banners"
            v-show="index === currentBanner"
            :key="banner.id"
            :src="banner.image"
            :alt="banner.alt"
            class="absolute w-40 h-24 object-cover rounded-lg"
          />
        </transition-group>
      </div>
    </div>

    <!-- Game List -->
    <div
      v-for="(game, index) in games"
      :key="game.name"
      class="bg-white p-4 rounded-lg shadow mb-4 flex items-center justify-between"
    >
      <div class="flex items-center gap-4">
        <div class="text-yellow-500 font-bold">{{ index + 1 }}</div>
        <img :src="game.logo" alt="" class="w-12 h-12 object-cover rounded" />
        <div>
          <div class="font-semibold">{{ game.name }}</div>
          <div class="text-sm text-gray-500">Mais de {{ game.players }} jogadores</div>
          <div class="text-sm">{{ game.description }}</div>
        </div>
      </div>
      <button class="bg-green-500 text-white px-4 py-2 rounded hover:bg-green-600">
        Jogo
      </button>
    </div>
    
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

import banner1 from '../assets/banner1.gif'
import banner2 from '../assets/banner2.gif'

const currentBanner = ref(0)
let intervalId = null

const banners = [
  { id: 1, image: banner1, alt: 'Banner 1' },
  { id: 2, image: banner2, alt: 'Banner 2' }
]

const games = [
  {
    name: "567br.com",
    players: "5.800.000",
    description: "Cadastre-se e ganhe R$87! Convide 1 pessoa, ganhe R$80. Bônus de check-in, saque alto e rápido, serviço de qualidade",
    logo: "/src/assets/game.png"
  },
  {
    name: "7kbet.com",
    players: "3.600.000",
    description: "Slots premium e saques rápidos. Ideal para jogadores frequentes.",
    logo: "/src/assets/game2.png"
  },
  {
    name: "999xp.com",
    players: "9.200.000",
    description: "Cadastre-se e ganhe R$99! Convide 1 pessoa: R$80. Bônus diário: R$1999. Check-in: R$999. Saque imediato",
    logo: "/src/assets/game3.png"
  },
  {
    name: "king299.com",
    players: "2.100.000",
    description: "Várias formas de ganhar: check-in, tarefas e sorteios.",
    logo: "/src/assets/game4.png"
  }
]

onMounted(() => {
  intervalId = setInterval(() => {
    currentBanner.value = (currentBanner.value + 1) % banners.length
  }, 3000)
})

onUnmounted(() => {
  if (intervalId) clearInterval(intervalId)
})
</script>

<style scoped>
body {
  background-color: #f3f4f6;
}
</style>
