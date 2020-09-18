<template>
  <article>
    <h1 v-if="page.title !== null" class="title">{{ page.title }}</h1>
    <h2 v-if="page.subtitle !== null" class="subtitle">{{ page.subtitle }}</h2>
    <nuxt-content :document="page" />
  </article>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const page = await $content(params.slug).fetch()

    return { page }
  },
}
</script>
