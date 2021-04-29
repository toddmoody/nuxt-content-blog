<template>
  <section class="recipies">
    <Receipe
      v-for="recipe in recipies"
      :key="recipe.id"
      :thumbnail="recipe.thumbnail"
      :title="recipe.title"
      :id="recipe.id"
      :previewText="recipe.previewText"
    />
  </section>
</template>

<script>
import Receipe from "@/components/Receipe";
export default {
  components: {
    Receipe,
  },
  asyncData() {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipies: [
            {
              id: "1",
              title: "Delicious pizza",
              previewText: "Awesome pizza",
              thumbnail:
                "https://joyfoodsunshine.com/wp-content/uploads/2016/09/easy-pizza-casserole-recipe-4-500x500.jpg",
            },
            {
              id: "2",
              title: "Delicious curry",
              previewText: "Awesome curry and rice",
              thumbnail:
                "https://assets.epicurious.com/photos/5df7c9efa9f50600094dffed/1:1/w_3137,h_3137,c_limit/COOK90_ButterPaneer_RECIPE_V2_121119_288.jpg",
            },
          ],
        });
      }, 1500);
    });
  },
};
</script>

<style scoped>
.recipies {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}
</style>