<template>
    <div>
        <p>Giới tính : {{ gender }}</p>
        <ul>
            <li><input type="radio" value="nam" v-model="gender"><label for="nam">nam</label></input></li>
            <li><input type="radio" value="nữ" v-model="gender"><label for="nữ">nữ</label></input></li>
            <li><input type="radio" value="khác" v-model="gender"><label for="khác">khác</label></input></li>
        </ul>
    </div>
</template>

<script setup>
    import { ref } from 'vue';

    const gender = ref("");
</script>

<style scoped>

</style>