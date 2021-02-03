<template>
  <div class="game__container">
    <img
      :src="game.img"
      :alt="game.alt"
      class=""
    >
    <nuxt-content :document="game" />
    <section>
      <MostRecommended />
    </section>
  </div>
</template>
<script>
import MostRecommended from '../../components/MostRecommended'

export default {
  components: {
    MostRecommended
  },
  async asyncData ({ $content, params }) {
    const game = await $content('games', params.slug).fetch()

    return { game }
  }
}
</script>

<style>

</style>
