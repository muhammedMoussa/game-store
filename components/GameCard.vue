<template>
  <div class="gameCard__container border-black">
    <pre>{{ game }}</pre>
    <NuxtLink
        :to="game.path"
        class="flex transition-shadow duration-150 ease-in-out shadow-sm hover:shadow-md xxlmax:flex-col"
    >
        Read More
    </NuxtLink>
  </div>
</template>

<script>
export default {
  props: {
    game: {
      type: Object,
      default: () => null
    }
  }
}
</script>
