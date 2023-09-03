<script setup lang="ts">
defineProps<{ rating: number }>()
</script>

<template>
    <div class="flex items-center justify-center min-h-screen">

        <!-- Card -->
        <div class="
            flex 
            flex-col 
            items-center
            gap-6
            
            p-8 
            m-6 
            
            rounded-2xl

            bg-gradient-to-b from-dark-blue/80 to-dark-blue/50
            ">
            <img src="../assets/img/illustration-thank-you.svg" alt="thank-you">

            <!-- Rating -->
            <div class="
                flex 
                flex-col 
                items-center 
                
                bg-dark-blue
                
                w-44
                p-1

                rounded-full
                ">
                <p class="text-orange text-sm">You selected {{ rating }} out of 5</p>
            </div>

            <!-- Callout -->
            <p class="text-white text-2xl">Thank you!</p>
            <p class="text-light-grey text-sm leading-6 text-center">
                We appreciate you taking the time to give a rating. If you 
                ever need more support, don't hesitate to get in touch!
            </p>
        </div>
    </div>
</template>

<style scoped>
* {
    box-sizing: border-box;
}
</style>