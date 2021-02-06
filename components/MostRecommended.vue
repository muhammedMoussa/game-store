<template>
  <div class="flex mostRecommended__container border-black">
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
