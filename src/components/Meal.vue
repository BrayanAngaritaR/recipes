<template>
   <div class="category_container">
      <img @click="openMealDetails" v-bind:src="meal.strMealThumb" v-bind:alt="meal.strMeal" width="300">
      <p><b>{{ meal.strMeal }}</b></p>
      <h6><b>Categoría</b>: {{ meal.strCategory }} | Orígen: {{ meal.strArea }}</h6>
   </div>
</template>

<script>
export default {
   props: ["meal"],
   methods: {
      openMealDetails(){
         this.$router.push("/meal/" + this.meal.idMeal);
      }
   }
}
</script>