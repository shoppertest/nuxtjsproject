<template>
  <section class="recipes">
      <Recipe 
      v-for="recipe in recipes"
      :key="recipe.id"
      :title="recipe.title"
      :thumbnail="recipe.thumbnail"
      :id="recipe.id"
      :previewText="recipe.previewText"
      
      />
      
  </section>
</template>

<script>
import Recipe from '@/components/Recipe'

export default {
components: {
    Recipe
},
asyncData(){
    return new Promise((resolve,reject)  => {
setTimeout(() => {
resolve({
    recipes: [
        {
            id: "1",
            title: "Delicious pizza",
            previewText: "Awesome Pizza",
            thumbnail: 'https://upload.wikimedia.org/wikipedia/commons/6/6d/Good_Food_Display_-_NCI_Visuals_Online.jpg'
        },
        {
            id: "2",
            title: "Delicious burger",
            previewText: "Awesome Burger",
            thumbnail: 'https://static.toiimg.com/photo/68283907.cms'
        }
    ]
})
},1500)
    })
}
};
</script>

<style>
.recipes {
display: flex;
flex-flow: row wrap;
justify-content: center;
align-items: center;
}


</style>