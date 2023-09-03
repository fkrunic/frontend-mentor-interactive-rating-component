<script setup lang="ts">
import SubmitCard from './components/SubmitCard.vue';
</script>

<template>
  <SubmitCard></SubmitCard>
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