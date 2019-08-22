<template>
  <section class="single-recipe">
      <h1>{{recipe.title}}</h1>
      <div>
          <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title"> 
      </div>
      <p>The recipe description.</p>
      <button><nuxt-link to="/recipes">Back</nuxt-link></button>
  </section>
</template>

<script>
export default {
asyncData(context){
    return new Promise((resolve,reject)  => {
setTimeout(() => {
resolve({
    recipe: [
        {
            id: "1",
            title: "Delicious pizza",
            previewText: "Awesome Pizza",
      descriptionText : "This is really delicious meal",      
            thumbnail: 'https://upload.wikimedia.org/wikipedia/commons/6/6d/Good_Food_Display_-_NCI_Visuals_Online.jpg'
        },
        {
            id: "2",
            title: "Delicious burger",
            previewText: "Awesome Burger",
            descriptionText : "This is really delicious meal",
            thumbnail: 'https://static.toiimg.com/photo/68283907.cms'
        }
    ].find(el => el.id === context.params.id )
})
},1500)
    })
}
};

</script>

<style>
.single-recipe {
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 30px;
}
.recipe-image {
    width: 100%
}
button {
  background-color: #008CBA; /* Green */
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
}
</style>