<template>
  <div class="max-w-md mx-auto p-4">
    
    <!-- Banner -->
    <div class="bg-green-700 text-white rounded-lg p-4 flex items-center gap-4 mb-6 relative h-24">

        <div>
        <h1 class="font-bold text-lg">BestGame.vip</h1>
      </div>
      <img src="../assets/banner1.gif" alt="Banner1" class="w-20 h-20 object-cover rounded-lg">
      <img src="../assets/banner2.gif" alt="Banner2" class="w-20 h-20 object-cover rounded-lg">
    </div>

    <!-- Game List -->
    <div v-for="(game, index) in games" :key="game.name" class="bg-white p-4 rounded-lg shadow mb-4 flex items-center justify-between">
      <div class="flex items-center gap-4">
        <div class="text-yellow-500 font-bold">{{ index + 1 }}</div>
        <img :src="game.logo" alt="" class="w-12 h-12 object-cover rounded">
        <div>
          <div class="font-semibold">{{ gamename }}</div>
          <div class="text-sm text-gray-500">Mais de {{ game.players }} jogadores</div>
          <div class="text-sm">{{ game.description }}</div>
        </div>
      </div>
      <button class="bg-green-500 text-white px-4 py-2 rounded hover:bg-green-600">Jogo</button>
    </div>
    
  </div>
  
</template>

<script>
export default {
  data() {
    return {
      games: [
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
    }
  }
}
</script>

<style scoped>
body {
  background-color: #f3f4f6; /* màu xám nhạt */
}
</style>
