<template>
  <div>
    <div v-for="doc in docs" :key="doc.slug">
      <nuxt-link :to="doc.path">{{ doc.title }}</nuxt-link>
      <p>{{ doc.description }}</p>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const docs = await $content("blog").sortBy("title").fetch();
    console.log("docs", docs);
    return { docs };
  },
};
</script>

<style>
</style>    