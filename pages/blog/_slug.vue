<template>
  <div>
    <nuxt-content :document="doc" />
    <h5 v-if="prev">
      Go
      <nuxt-link :to="prev.slug">back</nuxt-link>
    </h5>
    <h5 v-if="next">
      Go
      <nuxt-link :to="next.slug">forward</nuxt-link>
    </h5>
  </div>
</template>
 
<script>
export default {
  async asyncData({ $content, params }) {
    const doc = await $content(`blog/${params.slug}` || index).fetch();
    const [prev, next] = await $content("blog")
      .only(["title", "slug"])
      .sortBy("title", "asc")
      .surround(params.slug, { before: 1, after: 1 })
      .fetch();
    return { doc, prev, next };
  },
};
</script>

<style>
</style>