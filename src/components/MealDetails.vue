<template>
   <div v-if="meal">
      <h3>{{ meal.strMeal }} | {{ meal.strArea }}</h3>

      <img v-bind:src="meal.strMealThumb" v-bind:alt="meal.strMeal" width="300">
      <p>{{ meal.strCategory }}</p>

      <div class="text-center">
         ...
      </div>

      <h3>Ingredientes</h3>

      <p>{{ meal.strIngredient1 }} </p>
      <p>{{ meal.strIngredient2 }} </p>
      <p>{{ meal.strIngredient3 }} </p>
      <p>{{ meal.strIngredient4 }} </p>
      <p>{{ meal.strIngredient5 }} </p>
      <p>{{ meal.strIngredient6 }} </p>
      <p>{{ meal.strIngredient7 }} </p>
      <p>{{ meal.strIngredient8 }} </p>
      <p>{{ meal.strIngredient9 }} </p>
      <p>{{meal.strIngredient10 }} </p>
      <p>{{meal.strIngredient11 }} </p>
      <p>{{meal.strIngredient12 }} </p>
      <p>{{meal.strIngredient13 }} </p>
      <p>{{meal.strIngredient14 }} </p>
      <p>{{meal.strIngredient15 }} </p>
      <p>{{meal.strIngredient16 }} </p>
      <p>{{meal.strIngredient17 }} </p>
      <p>{{meal.strIngredient18 }} </p>
      <p>{{meal.strIngredient19 }} </p>
      <p>{{meal.strIngredient20 }}. </p>

      <h3>Medidas | Porciones</h3>

      <p>{{ meal.strMeasure1 }} {{ meal.strIngredient1 }}</p>
      <p>{{ meal.strMeasure2 }} {{ meal.strIngredient2 }}</p>
      <p>{{ meal.strMeasure3 }} {{ meal.strIngredient3 }}</p>
      <p>{{ meal.strMeasure4 }} {{ meal.strIngredient4 }}</p>
      <p>{{ meal.strMeasure5 }} {{ meal.strIngredient5 }}</p>
      <p>{{ meal.strMeasure6 }} {{ meal.strIngredient6 }}</p>
      <p>{{ meal.strMeasure7 }} {{ meal.strIngredient7 }}</p>
      <p>{{ meal.strMeasure8 }} {{ meal.strIngredient8 }}</p>
      <p>{{ meal.strMeasure9 }} {{ meal.strIngredient9 }}</p>
      <p>{{ meal.strMeasure10 }} {{ meal.strIngredient10 }}</p>
      <p>{{ meal.strMeasure11 }} {{ meal.strIngredient11 }}</p>
      <p>{{ meal.strMeasure12 }} {{ meal.strIngredient12 }}</p>
      <p>{{ meal.strMeasure13 }} {{ meal.strIngredient13 }}</p>
      <p>{{ meal.strMeasure14 }} {{ meal.strIngredient14 }}</p>
      <p>{{ meal.strMeasure15 }} {{ meal.strIngredient15 }}</p>
      <p>{{ meal.strMeasure16 }} {{ meal.strIngredient16 }}</p>
      <p>{{ meal.strMeasure17 }} {{ meal.strIngredient17 }}</p>
      <p>{{ meal.strMeasure18 }} {{ meal.strIngredient18 }}</p>
      <p>{{ meal.strMeasure19 }} {{ meal.strIngredient19 }}</p>
      <p>{{ meal.strMeasure20 }} {{ meal.strIngredient20 }}.</p>

      <h3>Instrucciones</h3>

      <p>{{ meal.strInstructions }}</p>

      <div class="text-center">
         ...
      </div>

      <h6 v-if="meal.strTags">
         Etiquetas: {{  meal.strTags }}
      </h6>

      <h6 v-if="meal.strCreativeCommonsConfirmed">
         Creative Commons {{  meal.strCreativeCommonsConfirmed }}
      </h6>

      <h6 v-if="meal.strDrinkAlternate">
         Bebida alternativa {{  meal.strDrinkAlternate }}
      </h6>

      <h6 v-if="meal.strSource">
         Fuente: <a v-bind:href="meal.strSource" target="_blank">{{  meal.strSource }}</a>
      </h6>

      <h6 v-if="meal.strYoutube">
         Vídeo en Youtube: <a v-bind:href="meal.strYoutube" target="_blank">{{  meal.strYoutube }}</a>
      </h6>
   </div>
   <div v-else>Cargando...</div>
</template>

<script>
   import axios from 'axios'

   export default{
      name: "MealDetails",
      data(){
         return {
            meal: null,
         }
      },
      mounted(){
         axios
            .get("https://themealdb.com/api/json/v1/1/lookup.php?i=" + this.$route.params.id)
            .then((res) => {
               this.meal = res.data.meals[0];
            })
            .catch((err) => {
               console.log(err);
            });
      }
   }
</script>



