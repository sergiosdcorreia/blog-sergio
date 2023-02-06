<template>
  <picture class="movie-image">
    <img :src="`/assets/movies/${src}`" :alt="alt" draggable="false" />
  </picture>
</template>

<script>
export default {
  name: 'ArticleImage',
  props: {
    src: {
      type: String,
      required: true,
    },
    alt: {
      type: String,
      required: true,
    },
  },
}
</script>
