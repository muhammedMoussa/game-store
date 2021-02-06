<template>
  <div class="mostPopular__container border-black">
    <!-- <h1>mostPopular__container</h1> -->
    <GameCard v-for="game of games" :key="game.slug" :game="game"/>
  </div>
</template>

<script>
import GameCard from './GameCard'

export default {
  props: {
    games: {
      type: Array,
      default: () => null
    }
  },
  components: {
    GameCard
  }
}
</script>