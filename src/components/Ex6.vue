<template>
    <div>
        <p>Sở thích : {{ hobbies }}</p>
        <ul>
            <li><input type="checkbox" value="đá bóng" v-model="hobbies">đá bóng</li>
            <li><input type="checkbox" value="gym" v-model="hobbies">gym</li>
            <li><input type="checkbox" value="bơi" v-model="hobbies">bơi</li>
            <li><input type="checkbox" value="code" v-model="hobbies">code</li>
        </ul>
    </div>
</template>

<script setup>
    import { ref } from 'vue';

    const hobbies = ref([])
</script>

<style scoped>

</style>