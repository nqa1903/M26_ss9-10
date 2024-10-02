<template>
    <div>
        <p>Màu sắc</p>
        <input type="color" v-model="colorValue">
        <p>Mã màu : {{ colorValue }}</p>
    </div>
</template>

<script setup>
    import { ref } from 'vue';

    const colorValue = ref("");
</script>

<style scoped>

</style>