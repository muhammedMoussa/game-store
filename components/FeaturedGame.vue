<template>
  <div class="featuredGame__container border-black">
    <pre>{{game}}</pre>
  </div>
</template>

<script>
export default {
  props: {
    game: {
      type: Array,
      default: () => null
    }
  }
}
</script>
