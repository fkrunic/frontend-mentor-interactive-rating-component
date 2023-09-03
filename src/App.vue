<script setup lang="ts">
import { ref } from 'vue';
import SubmitCard from './components/SubmitCard.vue';
import ThankYouCard from './components/ThankYouCard.vue';
import { SubmissionState } from './common';

const submissionState = ref({ kind: 'not-rated' } as SubmissionState)

const toggleRating = (rating: number): void => {
    submissionState.value = { kind: 'rated', rating }
}
</script>

<template>
  <Transition name="slide-fade">
    <SubmitCard 
      v-if="submissionState.kind == 'not-rated'"
      @submit-rating="toggleRating"
    ></SubmitCard>
    <ThankYouCard v-else :rating="submissionState.rating"></ThankYouCard>
  </Transition>
</template>

<style scoped>
* {
  box-sizing: border-box;
}

/* we will explain what these classes do next! */
.slide-fade-enter-active {
  transition: all 0.3s ease-out;
}

.slide-fade-leave-active {
  transition: all 0.3s ease-out;
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateX(20px);
  opacity: 0;
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