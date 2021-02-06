<template>
  <div class="container">
    <FeaturedGame :game="featured" />
    <MostRecommended :games="recommended" />
    <MostPopular :games="pupular" />
  </div>
</template>

<script>
import FeaturedGame from '../components/FeaturedGame'
import MostRecommended from '../components/MostRecommended'
import MostPopular from '../components/MostPopular'

export default {
  components: {
    FeaturedGame,
    MostRecommended,
    MostPopular
  },
  async asyncData ({ $content, params }) {
    const games = await $content('games', params.slug)
      .fetch()

    const featured = await $content('games', params.slug)
      .where({ tags: { $contains: ['featured'] } })
      .only(['title', 'description', 'img', 'slug', 'author'])
      .fetch()

    const recommended = await $content('games', params.slug)
      .where({ tags: { $contains: ['recommended'] } })
      .only(['title', 'rate', 'img'])
      .fetch()

    const pupular = await $content('games', params.slug)
      .where({ tags: { $contains: ['pupular'] } })
      .only(['title', 'rate', 'img'])
      .fetch()

    return {
      games,
      featured,
      recommended,
      pupular
    }
  }
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS */
/* .container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
} */

</style>
