<script setup lang="ts">
import SubmitCard from './components/SubmitCard.vue';
import ThankYouCard from './components/ThankYouCard.vue';
</script>

<template>
  <ThankYouCard :rating="4"></ThankYouCard>
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