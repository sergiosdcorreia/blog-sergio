<script setup>
const { path } = useRoute()

const { data: blogPost } = await useAsyncData(`content-${path}`, () => {
  return queryContent().where({ _path: path }).findOne()
})
</script>

<template>
  <main class="blog-container">
    <TheHero>
      <template #default>{{ blogPost.title }}</template>
      <template #subtitle>
        <BlogPostMeta
          :author="blogPost.author"
          :date="blogPost.dates.published"
          color="dark"
        />
      </template>
    </TheHero>
    <div class="content-doc">
      <ContentDoc></ContentDoc>
    </div>
  </main>
</template>
