<script setup lang="ts">
// import HelloWorld from './components/HelloWorld.vue'
import ButtonRating from './components/ButtonRating.vue';
</script>

<template>
  <div class="flex justify-center items-center min-h-screen">

    <!-- Card -->
    <div class="
      flex 
      flex-col 
      gap-4

      p-6
      m-4

      rounded-2xl

      bg-gradient-to-b from-dark-blue/80 to-dark-blue/50
      ">

      <!-- Star Icon -->
      <div class="flex items-center justify-center w-10 h-10 rounded-full bg-dark-blue">
        <img class="w-4" src="./assets/img/icon-star.svg" alt="rating">
      </div>

      <!-- Callout -->
      <p class="text-white text-2xl">How did we do?</p>
      <p class="text-light-grey text-sm leading-6">
        Please let us know how we did with your support request.
        All feedback is appreciated to help us improve our offering!
      </p>

      <!-- Rating Selection -->
      <div class="flex flex-row items-center justify-center mt-4 gap-4">
        <ButtonRating
          v-for="rating of [1,2,3,4,5]"
          :key="rating"
          :rating="rating"
          :isSelected="false"
        ></ButtonRating>
      </div>

      <!-- Submit Button -->
      <div class="
        flex 
        flex-row 
        justify-center 
        items-center 

        mt-2
        p-4

        bg-orange
        rounded-full
        ">
        <p class="text-white text-sm font-bold tracking-widest">SUBMIT</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
* {
  box-sizing: border-box;
}
</style>

<script lang="ts">
export default {
  data() {
    return {
      bodyClass: 'font-overpass bg-very-dark-blue'
    };
  },
  mounted() {
    document.body.className = this.bodyClass;
  },
  beforeDestroy() {
    // Reset the class when the component is destroyed
    document.body.className = '';
  }
};
</script>