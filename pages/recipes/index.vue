<template>
  <section class="recipes">
    <Recipe v-for="recipe in recipes" :key="recipe.id"
      :title="recipe.title"
      :previewText="recipe.previewText"
      :thumbnail="recipe.thumbnail"
      :id="recipe.id"
        />
  </section>
</template>

<script>
import Recipe from '@/components/Recipe'

export default {
  components: {
    Recipe
  },
  asyncData () {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipes : [
            {
              id: "1",
              title: "Herkullinen hampurilainen",
              previewText: "'vuoden paras uusi tuote' - palkinnon voittanut majoneesi!",
              thumbnail: "http://orlandofoodscene.com/wp-content/uploads/2013/02/CrookedSpoon1.jpg"
            },
            {
              id: "2",
              title: "Mereneläviä",
              previewText: "hienostuneella soijakastikkeella",
              thumbnail: "http://1.bp.blogspot.com/-mPS7uigsIF4/TvrggktOYeI/AAAAAAAAAiE/GPOZrUxBVQE/s1600/Bohol+Food+Photo21.jpg"
            }
          ]
        })
      }, 1000)
    })
  }
}
</script>


<style scoped>
  .recipes {
    display: flex;
    flex-flow: row wrap;
  }
</style>
