<script setup lang="ts">
defineProps<{rating: number, isSelected: boolean}>()
</script>

<template>
    <div class="
        flex 
        flex-row 
        items-center
        justify-center

        w-10
        h-10
        pt-0.5

        rounded-full
        
        bg-dark-blue

        group
        hover:bg-medium-grey
        hover:cursor-pointer
        ">
        <p class="
            text-medium-grey text-sm
            group-hover:text-white
            ">{{ rating }}</p>
    </div>
</template>

<style scoped>
* {
    box-sizing: border-box;
}
</style>