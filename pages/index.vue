<template>
  <div class="container">
    <FeaturedGame />
    <MostRecommended />
    <MostPopular />
    <ul>
      <li v-for="game of games" :key="game.slug">
        <NuxtLink 
          :to="{ name: 'games-slug', params: { slug: game.slug } }"
          class="flex transition-shadow duration-150 ease-in-out shadow-sm hover:shadow-md xxlmax:flex-col"
        >
          {{game.slug}}
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script>
import FeaturedGame from '../components/FeaturedGame'
import MostRecommended from '../components/MostRecommended'
import MostPopular from '../components/MostPopular'

export default {
    async asyncData({ $content, params }) {
    const games = await $content('games', params.slug)
      .fetch()

    return {
      games
    }
  },
  components: {
    FeaturedGame,
    MostRecommended,
    MostPopular
  }
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS */
/* .container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
} */


</style>
