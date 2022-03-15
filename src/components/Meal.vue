<template>
   <div class="category_container">
      <img @click="openMealDetails" v-bind:src="meal.strMealThumb" v-bind:alt="meal.strMeal" width="300">
      <p><b>{{ meal.strMeal }}</b></p>
   </div>
</template>

<script>
import App from "../App.vue";
export default {
    props: ["meal"],
    methods: {
        openMealDetails() {
            this.$router.push("/meal/" + this.meal.idMeal);
        }
    },
    components: { App }
}
</script>