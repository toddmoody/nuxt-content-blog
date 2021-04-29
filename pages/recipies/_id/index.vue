<template>
  <section class="single__recipe">
    <h1>{{ recipe.title }}</h1>
    <div>
      <img :src="recipe.thumbnail" :alt="recipe.title" />
      <p>{{ recipe.descriptionText }}</p>
    </div>
  </section>
</template>

<script>
export default {
  asyncData(context) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipe: [
            {
              id: "1",
              title: "Delicious pizza",
              previewText: "Awesome pizza",  
              descriptionText: "This really is a delicious looking meal",
              thumbnail:
                "https://joyfoodsunshine.com/wp-content/uploads/2016/09/easy-pizza-casserole-recipe-4-500x500.jpg",
            },
            {
              id: "2",
              title: "Delicious curry",
              previewText: "Awesome curry and rice",
              descriptionText: "This really is a delicious looking meal as well I think.",
              thumbnail:
                "https://assets.epicurious.com/photos/5df7c9efa9f50600094dffed/1:1/w_3137,h_3137,c_limit/COOK90_ButterPaneer_RECIPE_V2_121119_288.jpg",
            },
          ].find(el => el.id === context.params.id),
        });
      }, 1500);
    });
  },
};
</script>

<style scoped>
.single-recipe {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>