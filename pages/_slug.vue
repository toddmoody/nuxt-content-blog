<template>
  <div class="container">

      <nuxt-content :document="doc"></nuxt-content>

  </div>
</template>

<script>
export default {
    async asyncData({ $content, params }) {
        const doc = await $content(params.slug || "index").fetch()

        return { doc }
    }
}
</script>

<style>

</style>