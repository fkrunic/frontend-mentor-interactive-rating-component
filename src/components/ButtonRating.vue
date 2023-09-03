<script setup lang="ts">
defineProps<{rating: number, isSelected: boolean}>()
</script>

<template>
    <div class="flex flex-col items-center justify-center bg-medium-grey/50">
        <p class="text-medium-grey">{{ rating }}</p>
    </div>
</template>

<style scoped>
* {
    box-sizing: border-box;
}
</style>