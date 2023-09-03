<script setup lang="ts">
import { ref } from 'vue';
import ButtonRating from './ButtonRating.vue';
import { match, P } from 'ts-pattern'

type SubmissionState 
    = { kind: 'not-rated' }
    | { kind: 'rated', rating: number }

const submissionState = ref({ kind: 'not-rated' } as SubmissionState)

const toggleRating = (rating: number): void => {
    submissionState.value = { kind: 'rated', rating }
}

const isRatingSelected = (ratingOption: number, state: SubmissionState): boolean => {
    return match(state)
        .with({kind: 'not-rated'}, () => false)
        .with({kind: 'rated', rating: P.select()}, (r) => r == ratingOption)
        .exhaustive()
}

const isReadyToSubmit = (state: SubmissionState): boolean => {
    return state.kind == 'rated'
}

const emit = defineEmits(['submitRating'])

const handleSubmission = (state: SubmissionState): void => {
    if (state.kind == 'rated')  {
        console.log('Submitted: ' + state.rating )
        emit('submitRating', state.rating)
    }
}

// Submission button classes
const buttonClasses = 
    {
        ready: {
            div: ['bg-orange', 'hover:bg-white', 'hover:cursor-pointer'],
            p: ['text-white', 'group-hover:text-orange']
        },
        notReady: {
            div: ['bg-dark-blue'],
            p: ['text-very-dark-blue']
        }
    }

</script>

<template>
  <div class="flex justify-center items-center min-h-screen">

    <!-- Card -->
    <div class="
      flex 
      flex-col 
      gap-4

      p-6
      m-6

      rounded-2xl

      bg-gradient-to-b from-dark-blue/80 to-dark-blue/50
      ">

      <!-- Star Icon -->
      <div class="flex items-center justify-center w-10 h-10 rounded-full bg-dark-blue">
        <img class="w-4" src="../assets/img/icon-star.svg" alt="rating">
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
          :isSelected="isRatingSelected(rating, submissionState)"
          @rating-chosen="toggleRating"
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

        rounded-full
 
        group
        "
        :class="
            isReadyToSubmit(submissionState) 
                ? buttonClasses.ready.div 
                : buttonClasses.notReady.div
        "
        @click="handleSubmission(submissionState)"
        >
        <p class="
          text-sm 
          font-bold 
          tracking-widest
          "
          :class="
            isReadyToSubmit(submissionState)
                ? buttonClasses.ready.p
                : buttonClasses.notReady.p
          "
          >SUBMIT</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
* {
  box-sizing: border-box;
}
</style>
