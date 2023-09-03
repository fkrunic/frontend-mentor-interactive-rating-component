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

        rounded-full
        
        bg-dark-blue
        ">
        <p class="text-medium-grey text-sm">{{ rating }}</p>
    </div>
</template>

<style scoped>
* {
    box-sizing: border-box;
}
</style>