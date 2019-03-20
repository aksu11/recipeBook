<template>
  <section class="single-recipe">
    <h1>{{ recipe.title }}</h1>
    <div>
      <img class="recipe-img" :src="recipe.thumbnail" :alt="recipe.title">
    </div>
    <p>{{ recipe.descriptionText }}</p>
  </section>
</template>

<script>
export default {
  asyncData (context) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipe : [
            {
              id: "1",
              title: "Herkullinen hampurilainen",
              previewText: "'vuoden paras uusi tuote' - palkinnon voittanut majoneesi!",
              descriptionText: "Tämä on helppo valmistaa...",
              thumbnail: "http://orlandofoodscene.com/wp-content/uploads/2013/02/CrookedSpoon1.jpg"
            },
            {
              id: "2",
              title: "Mereneläviä",
              previewText: "hienostuneella soijakastikkeella",
              descriptionText: "Tämä on helppo valmistaa...",
              thumbnail: "http://1.bp.blogspot.com/-mPS7uigsIF4/TvrggktOYeI/AAAAAAAAAiE/GPOZrUxBVQE/s1600/Bohol+Food+Photo21.jpg"
            }
          ].find( r => r.id === context.params.id)
        })
      }, 1500)
    })
  }
}
</script>


<style scoped>
  .single-recipe {
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
  .recipe-img {
    width: 60vw;
    margin-bottom: 20px;
  }
  h1 {
    margin: 30px;
  }
</style>
