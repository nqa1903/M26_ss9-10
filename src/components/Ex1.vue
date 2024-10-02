<template>
    <div>
        <p>Email</p>
        <input type="text" v-model="email">
        <p>Giá trị {{ email }}</p>
    </div>
</template>

<script setup>
    import { ref } from 'vue';

    const email = ref("");
</script>

<style scoped>

</style>