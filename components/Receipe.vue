<template>
  <nuxt-link :to="'/recipies/' + id">
    <article class="recipies__article">
      <div
        class="recipies__article__thumbnail"
        :style="{ backgroundImage: 'url(' + thumbnail + ')' }"
      ></div>
      <h1>{{ title }}</h1>
      <p>{{ previewText }}</p>
    </article>
  </nuxt-link>
</template>

<script>
export default {
  props: ["thumbnail", "title", "previewText", "id"],
};
</script>

<style scoped>
.recipies__article {
  box-sizing: border-box;
  width: 280px;
  padding: 8px;
  border: 1px solid #ccc;
  box-shadow: 0 2px 2px #aaa;
  margin: 5px 5px;
}
.recipies__article__thumbnail {
  background-position: center;
  background-size: cover;
  width: 100%;
  height: 200px;
}
</style>