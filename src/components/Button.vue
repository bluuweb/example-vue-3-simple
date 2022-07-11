<script setup>
defineProps(["counter"]);

const emit = defineEmits(["increment"]);
</script>

<template>
    <button @click="emit('increment')">{{ counter }}</button>
</template>
