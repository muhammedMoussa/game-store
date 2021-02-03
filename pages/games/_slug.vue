<template>
  <div class="game__container">
    <nuxt-content :document="game" />
    <pre> {{ game }} </pre>

    <section>
        <MostRecommended />
    </section>
  </div>
</template>
<script>
import MostRecommended from '../../components/MostRecommended'

export default {
    async asyncData({ $content, params }) {
      const game = await $content('games', params.slug).fetch()

      return { game }
    },
    components: {
        MostRecommended
    }
}
</script>

<style>

</style>
